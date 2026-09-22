# 🆓 Features FREE do Bruno (Tudo que Você Precisa)

> Guia completo: o que está disponível no plano FREE do Bruno e como aproveitar ao máximo.

**Spoiler:** Você tem TUDO que precisa. Não pague nada. 💰

---

## ✅ O que Está FREE (Unlimited)

### 🔧 Requests & Collections

| Feature | Status | Limite | Uso |
|---------|--------|--------|-----|
| **Unlimited Requests** | ✅ FREE | Sem limite | Crie quantas requisições quiser |
| **Unlimited Collections** | ✅ FREE | Sem limite | Organize quantas collections precisar |
| **Unlimited Environments** | ✅ FREE | Sem limite | dev, staging, prod, etc |
| **Unlimited Folders** | ✅ FREE | Sem limite | Organize por domínios |
| **HTTP Methods** | ✅ FREE | Todos | GET, POST, PUT, DELETE, PATCH, etc |
| **Request Body Formats** | ✅ FREE | Todos | JSON, XML, Form-urlencoded, multipart, etc |

### 🔐 Autenticação & Headers

| Feature | Status | Uso |
|---------|--------|-----|
| **Basic Auth** | ✅ FREE | User:Pass |
| **Bearer Token** | ✅ FREE | OAuth 2.0, STS |
| **API Key** | ✅ FREE | Header ou query param |
| **Custom Headers** | ✅ FREE | Qualquer header customizado |
| **Cookies** | ✅ FREE | Persistent cookies |
| **SSL Verification** | ✅ FREE | Ignore self-signed certs (dev) |

### 📝 Scripting & Automação

| Feature | Status | Uso |
|---------|--------|-----|
| **Pre-request Scripts** | ✅ FREE | JavaScript antes do request |
| **Post-response Tests** | ✅ FREE | JavaScript depois da resposta |
| **Folder-level Scripts** | ✅ FREE | Executar antes de qualquer request da pasta |
| **Console Logs** | ✅ FREE | `console.log()` para debug |
| **Assertions** | ✅ FREE | `tests['nome'] = condition` |
| **Dynamic Variables** | ✅ FREE | `{{ $randomUUID }}`, `{{ $timestamp }}`, etc |

### 🔗 Fluxo & Encadeamento

| Feature | Status | Uso |
|---------|--------|-----|
| **bru.setNextRequest()** | ✅ FREE | Pular para próximo request |
| **bru.setEnvVar()** | ✅ FREE | Salvar variável de ambiente |
| **bru.getEnvVar()** | ✅ FREE | Ler variável de ambiente |
| **Flow Control** | ✅ FREE | `bru.runner.stopExecution()`, `skipRequest()` |
| **Conditional Logic** | ✅ FREE | if/else, loops em scripts |

### 💾 Variáveis & Escopo

| Feature | Status | Limit | Uso |
|---------|--------|-------|-----|
| **Environment Variables** | ✅ FREE | Unlimited | `{{ var }}` - aplicado globalmente |
| **Collection Variables** | ✅ FREE | Unlimited | Compartilhadas na collection |
| **Folder Variables** | ✅ FREE | Unlimited | Apenas nesta pasta (v4.1+) |
| **Request Variables** | ✅ FREE | Unlimited | Locais ao request |
| **Nested Access** | ✅ FREE | Unlimited | `{{ obj.field }}` |

### 📊 Collection Runner (Automação em Batch)

| Feature | Status | Uso |
|---------|--------|-----|
| **Sequential Execution** | ✅ FREE | Executar requests em ordem |
| **Parallel Execution** | ✅ FREE | Executar múltiplas em paralelo |
| **Data Files (CSV/JSON)** | ✅ FREE | Iterar sobre dados |
| **Iterations** | ✅ FREE | Repetir N vezes |
| **Delay Between Requests** | ✅ FREE | Rate limiting |
| **Export Results** | ✅ FREE | JSON com resultados |

### 🔄 Import/Export

| Feature | Status | Formatos |
|---------|--------|----------|
| **Import Collections** | ✅ FREE | Bruno, Insomnia, Postman, OpenAPI, cURL |
| **Export Collections** | ✅ FREE | Bruno (default), Postman, OpenAPI |
| **Share Collections** | ✅ FREE | Via Git (recomendado) |

### 🎨 Interface & Customização

| Feature | Status | Uso |
|---------|--------|-----|
| **Light/Dark Theme** | ✅ FREE | Alterne conforme preferência |
| **Syntax Highlighting** | ✅ FREE | JSON, XML, HTML, etc |
| **Response Tabs** | ✅ FREE | Status, Body, Headers, Cookies, Logs |
| **Search & Filter** | ✅ FREE | Buscar requests/folders |
| **Keyboard Shortcuts** | ✅ FREE | Ctrl+Enter, etc |

### 🔌 Integração

| Feature | Status | Uso |
|---------|--------|-----|
| **Git Integration** | ✅ FREE | Sync automático em `.bru` files |
| **Command Line (CLI)** | ✅ FREE | `bru run` para CI/CD |
| **Webhooks** | ✅ FREE | Chamar endpoints externos |

---

## ❌ O que É PAGO (Ignore)

| Feature | Plano | Por quê? |
|---------|-------|---------|
| **Cloud Sync** | Pro | Use Git em vez disso |
| **Team Workspaces** | Pro | Use organização GitHub para time |
| **Cloud Backup** | Pro | Git é sua backup |
| **Priority Support** | Pro | Community + docs são suficientes |
| **Custom Domains** | Enterprise | Não é necessário |

**TL;DR:** Você NÃO precisa de nenhum plano pago. Git resolve tudo.

---

## 🎯 Stack Completo com FREE

### Seu Setup (100% Gratuito)

```
┌─────────────────────┐
│   Bruno (FREE)      │ ← Cliente HTTP
│ • Collections       │
│ • Pre/Post scripts  │
│ • Collection Runner │
└──────────┬──────────┘
           │
           ├─────────────────────┐
           │                     │
      ┌────▼─────┐      ┌───────▼──────┐
      │  Git     │      │ CI/CD        │
      │ (GitHub) │      │ (Actions)    │
      └──────────┘      └──────────────┘
           │
      ┌────▼──────────────┐
      │ BFF API          │
      │ (Java/Spring)    │
      │ • STS            │
      │ • Tributos       │
      │ • Pix            │
      │ • DDA            │
      └─────────────────┘
```

### Features que Você Vai Usar

1. **Pre-request Script** (Autenticação STS com cache)
2. **Post-response Tests** (Validar respostas)
3. **bru.setNextRequest()** (Encadear requests)
4. **Collection Runner** (Testar múltiplos fluxos)
5. **Folder Variables** (Config por domínio)
6. **Git Integration** (Compartilhar com time)
7. **Dynamic Variables** (IDs aleatórios, timestamps)

---

## 💡 Estratégias para Não Precisar Pagar

### 1. Cloud Sync → Git (FREE)

❌ **Pago:**
```
Bruno Pro → Cloud Sync → Automático
```

✅ **FREE:**
```
Bruno FREE → Git → Manual push (5 seg)
git add .
git commit -m "Update: novo endpoint"
git push
```

**Economiza:** R$ 300/ano

---

### 2. Team Workspaces → GitHub Organization (FREE)

❌ **Pago:**
```
Bruno Team → Central workspace → Time colabora
```

✅ **FREE:**
```
GitHub Organization → Repositório único → Git workflow (PRs, branches)
```

**Economiza:** R$ 1500+/ano

---

### 3. Backup → Git (FREE)

❌ **Pago:**
```
Bruno Cloud → Backup automático
```

✅ **FREE:**
```
Git Commit → GitHub → Sempre versionado
```

**Economiza:** R$ 300/ano

---

## 📋 Checklist: Configuração Completa (FREE)

### Setup Inicial
- [ ] Download Bruno (grátis)
- [ ] Criar repositório GitHub
- [ ] Clonar Bruno repo local
- [ ] Adicionar `.env.example` ao repo
- [ ] Adicionar `.gitignore` (secrets)

### Collections
- [ ] Criar folder structure (Auth, Pagamentos, etc)
- [ ] STS-Token request com **pre-request caching**
- [ ] Requests autenticados com `Bearer {{ access_token }}`
- [ ] Tests em todos os requests

### Automação
- [ ] Collection Runner configurado
- [ ] CSV/JSON de dados de teste
- [ ] Scripts de batch em pre-request folder
- [ ] CLI scripts para CI/CD

### Git Workflow
- [ ] Commits regulares de `.bru` files
- [ ] `.env.local` no `.gitignore`
- [ ] PRs para code review
- [ ] Branches por feature

---

## 🚀 Exemplo Real: Setup Completo (Totalmente FREE)

### Passo 1: Criar STS Token com Cache

```javascript
// Pre-request: STS-Token
const cached = bru.getEnvVar('access_token');
const expiry = bru.getEnvVar('token_expiry');

if (cached && Date.now() < expiry) {
  console.log('✅ Token em cache. Pulando STS.');
  bru.setNextRequest('Primeira-Requisicao');
} else {
  console.log('🔄 Obtendo token do STS...');
}

// Test: STS-Token (pós-resposta)
const body = res.getBody();
bru.setEnvVar('access_token', body.access_token);
bru.setEnvVar('token_expiry', Date.now() + (body.expires_in * 1000) - 60000);
```

**Resultado:** ✅ STS chamado 1x por hora (econômico, cumpre rate limits)

---

### Passo 2: Encadear Fluxos

```javascript
// Test: Consultar-Tributo
if (res.getStatus() === 200 && res.getBody().status === 'PENDENTE') {
  bru.setEnvVar('tributacao_id', res.getBody().id);
  bru.setNextRequest('Validar-Tributo');
}

// Test: Validar-Tributo
if (res.getStatus() === 200) {
  bru.setEnvVar('validacao_id', res.getBody().validacaoId);
  bru.setNextRequest('Pagar-Tributo');
}
```

**Resultado:** ✅ Fluxo completo: Consultar → Validar → Pagar (automático)

---

### Passo 3: Collection Runner (Batch)

**dados.csv:**
```csv
tributacao_id,valor,competencia
TR-001,1500.00,2026-09
TR-002,2300.50,2026-09
TR-003,890.25,2026-09
```

**No Collection Runner:**
1. Selecionar pasta "Pagamentos/Tributos"
2. Marcar "Parallel"
3. Carregar `dados.csv`
4. Executar 3 vezes em paralelo

**Resultado:** ✅ Testar 3 tributos simultâneamente

---

### Passo 4: GitHub + CI/CD (FREE)

**.github/workflows/test.yml:**
```yaml
name: Test Collection
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: bru run .bruno/collections/ --env staging
```

**Resultado:** ✅ Testes rodam automaticamente a cada push

---

## 🎁 Bônus: Features Avançadas (Sem Pagar)

### 1. Variáveis Dinâmicas (Sempre FREE)

```
{{ $randomUUID }}        // 550e8400-e29b-41d4-a716-446655440000
{{ $randomInt }}         // 7392
{{ $timestamp }}         // 1695312000
{{ $isoTimestamp }}      // 2023-09-21T12:00:00Z
{{ $date }}              // 2023-09-21
{{ $env }}               // development
```

### 2. Nested Variables (Sempre FREE)

```javascript
// Em Body:
{
  "user_id": "{{ user.id }}",
  "credentials": "{{ auth.token }}"
}

// Em Pre-request:
bru.setEnvVar('user.id', '12345');
bru.setEnvVar('auth.token', 'abc123');
```

### 3. Console & Debugging (Sempre FREE)

```javascript
console.log('Debug:', variavel);
console.error('Erro:', erro.message);
console.table(arrayData);  // Formata como tabela
```

---

## 🎯 Resumo: Por que NÃO Pagar

| Necessidade | Pago | FREE | Vencedor |
|-------------|------|------|----------|
| Sync collections | Cloud Sync | Git | **Git** (versionado) |
| Compartilhar time | Team Workspace | GitHub Org | **GitHub** (PRs, code review) |
| Backup | Cloud Backup | Git | **Git** (infinito) |
| Automação | Webhooks | CLI + Actions | **CLI** (integrado) |
| Suporte | Premium Support | Community | **Community** (rápido) |

**Conclusão:** Bruno FREE + Git = Setup corporativo completo

---

## 📞 Próximos Passos

1. Instale Bruno (grátis)
2. Configure Git no seu projeto
3. Crie sua primeira collection
4. Faça commit no Git
5. Compartilhe com o time via GitHub

**Não pague nada. Aproveite tudo.**

---

**Próximo:** [Exemplos de Collections](./exemplos/README.md)
