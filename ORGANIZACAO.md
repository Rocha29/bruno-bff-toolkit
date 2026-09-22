# 🗂️ Organização e Controle de Collections no Bruno

> Como estruturar collections de forma profissional, versionável no Git e escalável para o time.

---

## 📦 Estrutura Recomendada

### Nível 1: Repositório Git

```
bruno-bff-api/
├── .gitignore              ← IMPORTANTE: não commita .env real
├── .env.example            ← COMMITA: template com variáveis
├── README.md
├── CONTRIBUIR.md
│
├── .bruno/
│   ├── collections/
│   │   ├── auth/
│   │   ├── pagamentos/
│   │   └── relatorios/
│   ├── bruno.json          ← Metadata da collection
│   └── .env.local          ← GITIGNORED: suas credenciais
│
└── exemplos/
    ├── requests-curl/
    ├── dados-teste/
    └── documentacao/
```

### Nível 2: Collections (dentro do .bruno/)

```
.bruno/collections/
│
├── auth/
│   ├── STS-Token.bru          ← Pre-request: cache token
│   ├── Refresh-Token.bru
│   └── Validate-Token.bru
│
├── pagamentos/
│   ├── tributos/
│   │   ├── Consultar.bru      ← Test: setEnvVar + setNextRequest
│   │   ├── Validar.bru
│   │   ├── Pagar.bru
│   │   └── Cancelar.bru
│   │
│   ├── pix/
│   │   ├── Criar-Chave.bru
│   │   ├── Enviar.bru
│   │   └── Receber.bru
│   │
│   └── dda/
│       ├── Listar.bru
│       ├── Confirmar.bru
│       └── Cancelar.bru
│
├── relatorios/
│   ├── Dashboard.bru
│   └── Exportar.bru
│
└── utils/
    ├── Health-Check.bru
    └── Version-Info.bru
```

---

## 🔧 Configuração Inicial (Git + Bruno)

### 1. Criar `.gitignore` (CRÍTICO)

```gitignore
# Variáveis sensíveis (NUNCA commita)
.env
.env.local
.env.*.local

# Arquivos de sistema
.DS_Store
Thumbs.db
*.log

# Dependências (se houver)
node_modules/
*.lock

# Backups
*.bak
*.backup

# IDE
.vscode/
.idea/
*.swp

# Temporários
/tmp/
/temp/
```

### 2. Criar `.env.example` (COMMITA)

```env
# ===== AUTENTICAÇÃO =====
STS_URL=https://sts.sandbox.local
STS_CLIENT_ID=seu-client-id-aqui
STS_CLIENT_SECRET=seu-client-secret-aqui
STS_SCOPE=api

# ===== ENDPOINTS =====
GATEWAY_URL=http://localhost:9090
PAGAMENTOS_URL=http://localhost:8081
RELATORIOS_URL=http://localhost:8082

# ===== TIMEOUTS =====
REQUEST_TIMEOUT=30000
RETRY_MAX=3

# ===== AMBIENTE =====
ENVIRONMENT=development
DEBUG=true
```

### 3. Instruir o time (DOCUMENTAR)

Crie um arquivo `SETUP_LOCAL.md`:

```markdown
## Setup Local (5 minutos)

1. Clone o repo
   git clone https://github.com/seu-time/bruno-bff-api.git

2. Configure variáveis
   cp .env.example .env
   # Edite .env com suas credenciais

3. Abra em Bruno
   - File → Open Collection
   - Selecione .bruno/collections/

4. Teste
   - Vá para Auth → STS-Token
   - Envie (Ctrl + Enter)
   - Token será cacheado automaticamente
```

---

## 📊 Variáveis por Scope (Hierarquia)

```
┌─────────────────────────────────────┐
│       VARIÁVEIS DINÂMICAS           │ Sem config (sempre disponíveis)
│    {{ $randomUUID }}, {{ $date }}   │
└─────────────────────────────────────┘
             ↓ Substitui
┌─────────────────────────────────────┐
│        GLOBAL (Global)              │ Em Settings → Globals (raro usar)
│     Compartilhadas com TODAS        │
│       as collections/environments   │
└─────────────────────────────────────┘
             ↓ Substitui
┌─────────────────────────────────────┐
│      ENVIRONMENT (Ambiente)         │ Em Settings → Environments
│   dev, staging, prod (switch fácil) │
│        {{ host }}, {{ sts_url }}    │
└─────────────────────────────────────┘
             ↓ Substitui
┌─────────────────────────────────────┐
│      COLLECTION (Collection)        │ Em Settings (collection-level)
│  Compartilhadas nesta collection    │
│        {{ api_timeout }}            │
└─────────────────────────────────────┘
             ↓ Substitui
┌─────────────────────────────────────┐
│         FOLDER (Folder)             │ Em Settings (folder-level)
│    Apenas nesta pasta (v4.1+)       │
│    {{ tributo_retry_max }}          │
└─────────────────────────────────────┘
             ↓ Substitui
┌─────────────────────────────────────┐
│        REQUEST (Request)            │ Em request level
│         Apenas neste request        │
│      {{ local_id }}                 │
└─────────────────────────────────────┘
```

### Exemplo Prático

**Environment variables (.env):**
```
host=http://localhost:8080
sts_url=https://sts.sandbox.local
```

**Collection variables (Settings → Variables):**
```json
{
  "timeout": "30000",
  "retry_max": "3"
}
```

**Folder variables (Folder → Settings → Variables):**
```json
{
  "tributo_retry_max": "2",
  "tributo_base_path": "/api/pagamentos/tributos"
}
```

**Request variables (Pre-request script):**
```javascript
// Local ao request
const requestId = bru.utils.generateUUID();
```

---

## 🔄 Workflow Git + Bruno (Pro)

### Cenário: Adicionar novo endpoint

#### 1. Criar branch
```bash
git checkout -b feature/pix-transfer
```

#### 2. Editar em Bruno
- Abra a collection em Bruno
- Crie novo request: `Pagamentos/Pix/Transfer.bru`
- Configure pre-request, test, etc
- **Bruno salva automaticamente em .bru file**

#### 3. Commitar
```bash
git add .bruno/collections/pagamentos/pix/Transfer.bru
git commit -m "Add: Pix transfer endpoint com tests"
```

#### 4. Pushar
```bash
git push origin feature/pix-transfer
```

#### 5. PR + Code Review
- Abra PR no GitHub
- Time revisa os .bru files (diff legível!)
- Aprova → merge

#### 6. Pull na branch principal
```bash
git checkout main
git pull origin main
# Collection atualiza automaticamente em Bruno
```

---

## 🚀 Melhores Práticas

### ✅ Faça

```
✅ Commitar .env.example (template)
✅ Usar .gitignore para .env real
✅ Nomear requests com verbos: Get-User, Create-Token, Delete-Invoice
✅ Usar folder variables para configurações por domínio
✅ Adicionar tests em todo request (validar status, response)
✅ Cache tokens STS com expiry
✅ Commitar .bru files (são texto, diff legível)
✅ Documentar em README.md como reproduzir fluxos
```

### ❌ Não Faça

```
❌ Commitar .env real (secrets vazam!)
❌ Hardcoding URLs/credenciais em requests
❌ Duplicar lógica de autenticação (use pre-request global)
❌ Deixar requests com TODO's sem resolver
❌ Commitar backups duplicados (.bru.backup)
❌ Mudar nomes de folders frequentemente (quebra histórico)
❌ Usar Global variables para tudo (difícil de debugar)
```

---

## 📋 Estrutura de Folders (Domínios)

### Opção 1: Por Domínio (Recomendado)

```
collections/
├── auth/                 ← Tudo relacionado a autenticação
├── pagamentos/          ← Tributos, Pix, DDA
├── relatorios/          ← Extratos, dashboards
└── admin/               ← Operações administrativas
```

**Vantagem:** Fácil navegar, clear separation of concerns

### Opção 2: Por Fluxo (Se tiver poucos requests)

```
collections/
├── fluxo-tributo-simples/     ← Consultar → Validar → Pagar
├── fluxo-pix-complexo/        ← Criar chave → Enviar → Confirmar
└── utilitarios/               ← Health check, etc
```

**Vantagem:** Organizado por caso de uso

---

## 🎛️ Collection Settings (Configuração Profissional)

### 1. Abrir Settings da Collection

Em Bruno: Clique direito na collection → **Settings**

### 2. Configurar Pre-request Global (Opcional)

```javascript
// Executado ANTES de qualquer request nesta collection
console.log('🚀 Starting request from collection:', bru.collectionName);

// Setup global (ex: adicionar header padrão)
const version = bru.getCollectionVar('api_version') || '1.0';
```

### 3. Variáveis da Collection

```json
{
  "api_version": "1.0",
  "timeout": "30000",
  "max_retries": "3",
  "log_level": "debug"
}
```

### 4. Scripts (se suportado)

Bruno permite pré-scripts em Collection level (v4.1+)

---

## 🔐 Proteção de Secrets

### NÃO FAZER (❌ Vazamento)
```javascript
// ❌ NUNCA
const token = "sk-abc123xyz789";  // Hardcoded!
```

### FAZER (✅ Seguro)
```javascript
// ✅ Use variáveis de ambiente
const sts_secret = bru.getEnvVar('STS_CLIENT_SECRET');
const token = getTokenFromSTS(sts_secret);  // Via .env.local
```

### .env.example (Safe to commit)
```env
STS_CLIENT_SECRET=ADICIONE_SUA_SECRET_AQUI
```

### .env.local (NEVER commit)
```env
STS_CLIENT_SECRET=abc123xyz789real_secret
```

---

## 📊 Exemplo Completo: Estrutura Real

```
meu-bff-api/
│
├── .gitignore
├── .env.example
├── README.md
├── SETUP_LOCAL.md
├── LICENSE (MIT)
│
├── .bruno/
│   ├── bruno.json
│   │
│   └── collections/
│       │
│       ├── auth/
│       │   ├── bruno.json
│       │   ├── STS-Token.bru
│       │   │   ├── @request
│       │   │   ├── @pre-request
│       │   │   ├── @test
│       │   │   └── @response
│       │   └── Validate-Token.bru
│       │
│       └── pagamentos/
│           ├── tributos/
│           │   ├── Consultar.bru
│           │   │   ├── @test
│           │   │   │   └── bru.setEnvVar('tributacao_id', ...)
│           │   │   │   └── bru.setNextRequest('Validar-Tributo')
│           │   │   └── @response
│           │   │
│           │   ├── Validar.bru
│           │   ├── Pagar.bru
│           │   └── Cancelar.bru
│           │
│           └── pix/
│               ├── Criar-Chave.bru
│               └── Enviar.bru
│
├── exemplos/
│   ├── requests-curl/
│   │   ├── auth-sts-token.sh
│   │   ├── pagamentos-tributos.sh
│   │   └── README.md
│   │
│   └── postman-collection.json (para quem usa Postman)
│
└── docs/
    ├── FLUXOS.md (diagramas dos fluxos)
    ├── TROUBLESHOOTING.md
    └── FAQ.md
```

---

## ✨ Checklist: Collections Prontas para o Time

Antes de commitar:

- [ ] Todos os requests têm `.bru` files no Git
- [ ] Nenhum `.env` real foi commitado (apenas `.env.example`)
- [ ] Todos os requests têm `Authorization: Bearer {{ access_token }}`
- [ ] STS-Token request tem pre-request com cache logic
- [ ] Cada request tem pelo menos um test básico
- [ ] Folder variables estão definidas (folder/Settings)
- [ ] `.gitignore` está configurado corretamente
- [ ] README.md explica a estrutura
- [ ] Exemplo de setup está em SETUP_LOCAL.md
- [ ] Nenhum hardcoding de credentials

---

## 📞 Troubleshooting

**P: Mudei um request em Bruno, mas não apareceu no Git?**  
R: Bruno salva automaticamente. Rode `git status` para ver mudanças. Se não aparecer, verifique se a pasta está dentro de `.bruno/`.

**P: Clonei o repo, mas as variáveis não funcionam?**  
R: Faça: `cp .env.example .env` e edite `.env` com suas credenciais.

**P: Como compartilhar collection com o time?**  
R: Commit os `.bru` files, push pro GitHub, time faz pull. Bruno carrega automaticamente.

**P: Posso usar a mesma collection para dev + staging?**  
R: Sim! Use Environments: crie `dev.bru` e `staging.bru` com variáveis diferentes. Alterne em Bruno.

---

**Próximo:** [FEATURES_FREE.md](./FEATURES_FREE.md) — O que usar do Bruno FREE
