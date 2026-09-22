# 🚀 Bruno Toolkit para BFF Java/Spring Boot

> Guia completo, prático e gratuito para migração Insomnia → Bruno com foco em Backend for Frontend (BFF).

**Status:** ✅ Production Ready | **Licença:** MIT | **Versão:** 1.0.0

---

## 📋 O que você encontra aqui?

Uma **documentação viva** com tudo que você precisa para:

- ✅ Migrar do Insomnia para Bruno **sem ficar preso**
- ✅ Organizar collections de forma **profissional e versionável** no Git
- ✅ Aproveitar **100% dos recursos FREE** do Bruno
- ✅ Implementar **STS token caching**, chamadas encadeadas, fluxos complexos
- ✅ Resolver problemas comuns rapidinho
- ✅ Ganhar **produtividade no dia-a-dia**

---

## 🎯 Estrutura do Repositório

```
bruno-bff-toolkit/
│
├── 📄 README.md (você está aqui)
├── 📄 QUICK_START.md (começar em 5 minutos)
├── 📄 ORGANIZACAO.md (como estruturar collections)
├── 📄 FEATURES_FREE.md (o que usar do free)
│
├── 📁 guias/
│   ├── 01-Insomnia-vs-Bruno.md (top 5 mudanças)
│   ├── 02-STS-Token-Caching.md (autenticação otimizada)
│   ├── 03-Encadeamento-Requests.md (fluxos complexos)
│   ├── 04-Variáveis-e-Escopos.md (variável por scope)
│   └── 05-Collection-Runner.md (paralelização)
│
├── 📁 ferramentas/
│   ├── bruno-speed-start.html (guia interativo pra iniciantes)
│   ├── bruno-toolkit.html (6 ferramentas integradas)
│   └── README.md (como usar)
│
├── 📁 exemplos/
│   ├── colecao-bff-tributos/ (exemplo completo com .env, requests, etc)
│   ├── colecao-bff-pix/ (payments com Pix)
│   └── colecao-bff-dda/ (débito automático)
│
└── 📁 .bruno/ (gitignored — suas requests e configs locais)
    └── .env.local (NÃO commitar variáveis sensíveis)
```

---

## ⚡ Quick Start (5 minutos)

### 1. Clonar este repositório
```bash
git clone https://github.com/SEU_USUARIO/bruno-bff-toolkit.git
cd bruno-bff-toolkit
```

### 2. Abrir no Bruno
- Abra Bruno
- Clique em **"File → Open Collection"**
- Selecione a pasta `exemplos/colecao-bff-tributos/`

### 3. Configurar variáveis
- Copie `.env.example` para `.env`
- Edite com seus dados (sts_url, client_id, etc)
- Pronto!

### 4. Executar primeira request
- Vá para **Auth → STS-Token**
- Clique **Send** (ou Ctrl + Enter)
- ✅ Token será cacheado automaticamente

---

## 📚 Documentação Principal

### Para Iniciantes
1. **[QUICK_START.md](./QUICK_START.md)** — Começar em 5 min
2. **[guias/01-Insomnia-vs-Bruno.md](./guias/01-Insomnia-vs-Bruno.md)** — Top 5 mudanças

### Intermediários
3. **[ORGANIZACAO.md](./ORGANIZACAO.md)** — Estrutura profissional de collections
4. **[guias/02-STS-Token-Caching.md](./guias/02-STS-Token-Caching.md)** — Autenticação otimizada
5. **[guias/03-Encadeamento-Requests.md](./guias/03-Encadeamento-Requests.md)** — Fluxos complexos

### Avançado
6. **[FEATURES_FREE.md](./FEATURES_FREE.md)** — O que usar do free (e o que não usar)
7. **[guias/04-Variáveis-e-Escopos.md](./guias/04-Variáveis-e-Escopos.md)** — Scopes e herança
8. **[guias/05-Collection-Runner.md](./guias/05-Collection-Runner.md)** — Testes em batch

---

## 🛠️ Ferramentas Interativas

Abra no navegador (funciona offline):

- **[bruno-speed-start.html](./ferramentas/bruno-speed-start.html)** — Guia interativo pra iniciantes
  - Top 5 mudanças
  - Setup 1º dia
  - 5 snippets prontos
  - Troubleshooting

- **[bruno-toolkit.html](./ferramentas/bruno-toolkit.html)** — Suite completa (6 ferramentas)
  - Referência rápida
  - Gerador de scripts
  - Organizador de variáveis
  - Checklist
  - Construtor de fluxos
  - Documentação visual

---

## 📦 Exemplos de Collections

Cada pasta em `exemplos/` é uma collection pronta para usar:

### `colecao-bff-tributos/`
- Estrutura completa de folders (Auth, Pagamentos/Tributos)
- Pre-requests com STS token caching
- Fluxo encadeado: Consultar → Validar → Pagar
- Tests com assertions

**Como usar:**
```bash
cd exemplos/colecao-bff-tributos/
# Copie o .env.example para .env local
# Edite com suas credenciais
# Abra em Bruno: File → Open Collection
```

---

## 🎯 Organização de Collections (Git + Versionamento)

Ver **[ORGANIZACAO.md](./ORGANIZACAO.md)** para:

✅ Como estruturar folders por domínio  
✅ Variáveis por scope (Environment, Collection, Folder, Global)  
✅ Como commitar collections no Git (sem expor secrets)  
✅ Workflow recomendado (branches, PRs, code review)  
✅ `.gitignore` apropriado para Bruno  

**TL;DR:**
```
.bruno/
├── .env (NEVER commit — add ao .gitignore)
├── .env.example (commit isso — é um template)
├── collections/
│   └── meu-bff/
│       ├── Auth/
│       │   └── STS-Token.bru
│       ├── Pagamentos/
│       │   └── Tributos/
│       │       └── Consultar.bru
│       └── bruno.json
└── .gitignore
```

---

## 🆓 Features FREE do Bruno (Tudo que Você Precisa)

Ver **[FEATURES_FREE.md](./FEATURES_FREE.md)** para lista completa.

**O que está disponível (FREE):**
- ✅ Unlimited requests e collections
- ✅ Pre-request scripts (Javascript)
- ✅ Post-response tests (Javascript)
- ✅ Folder-level variables
- ✅ Collection Runner (batch execution)
- ✅ Encadeamento com `bru.setNextRequest()`
- ✅ STS token caching e refresh
- ✅ Importação/Exportação (Insomnia, Postman, OpenAPI)
- ✅ Git sync automático
- ✅ Themes (light/dark)
- ✅ Variáveis dinâmicas (`$randomUUID`, `$timestamp`, etc)

**O que é PAGO (ignore):**
- ❌ Cloud sync (mas você tem Git!)
- ❌ Team workspaces (use organizações do GitHub)
- ❌ Enterprise features

---

## 🚀 Ganhe Tempo Com Isto

### Snippets Prontos (Copy & Paste)
```javascript
// STS Token com Cache
const cachedToken = bru.getEnvVar('access_token');
const tokenExpiry = bru.getEnvVar('token_expiry');
if (cachedToken && Date.now() < tokenExpiry) {
  bru.setNextRequest('ProximaRequisicao');
}
```

Mais em: `guias/02-STS-Token-Caching.md`

### Variáveis Dinâmicas
```
{{ $randomUUID }}       // ID aleatório
{{ $timestamp }}        // Unix timestamp
{{ $isoTimestamp }}     // ISO format
{{ $randomInt }}        // Número aleatório
```

### Atalhos
```
Ctrl + Enter     // Enviar request
Ctrl + Shift + E // Collection Runner
Ctrl + D         // Duplicate request
```

---

## 📖 Como Contribuir

Encontrou um bug? Quer adicionar um guia?

1. Fork este repositório
2. Crie uma branch: `git checkout -b feature/minha-contribuicao`
3. Commit: `git commit -m "Add: novo guia sobre X"`
4. Push: `git push origin feature/minha-contribuicao`
5. Abra um Pull Request

---

## ❓ FAQ

**P: Preciso pagar para usar Bruno?**  
R: Não! Todos os recursos que você precisa (STS caching, fluxos, tests, Git sync) estão no FREE.

**P: Posso usar em produção?**  
R: Sim! Bruno é estável e confiável. Use para testes, documentação viva, automação.

**P: Como sincronizar com Git?**  
R: Bruno salva as collections em `.bru` files (git-friendly). Commite normalmente. Veja `ORGANIZACAO.md`.

**P: E se eu tiver secrets (.env)?**  
R: Nunca commita `.env` real. Use `.env.example` como template e adicione ao `.gitignore`.

**P: Como distribuir collections para o time?**  
R: Commita no Git, o time clona e abre em Bruno. Pronto!

---

## 📞 Suporte

- 🐛 [Issues](https://github.com/SEU_USUARIO/bruno-bff-toolkit/issues) — Reporte problemas
- 💬 [Discussions](https://github.com/SEU_USUARIO/bruno-bff-toolkit/discussions) — Perguntas
- 📚 [Bruno Docs](https://docs.usebruno.com/) — Documentação oficial

---

## 📝 Licença

MIT — Use livremente, inclusive comercialmente. Ver [LICENSE](./LICENSE)

---

**Feito com ❤️ para QA → Backend developers**

Última atualização: 2026-09-21 | Bruno v4.1.0
