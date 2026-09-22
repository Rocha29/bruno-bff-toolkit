# 🚀 Subir no GitHub Público

Passo-a-passo para colocar este projeto em seu GitHub público.

---

## 📋 Pré-requisitos

- ✅ Conta GitHub criada (https://github.com/signup)
- ✅ Git instalado (`git --version`)
- ✅ Este projeto na sua máquina

---

## 🎯 Passo 1: Criar Repositório no GitHub

### 1.1 Ir para GitHub

https://github.com/new

### 1.2 Preencher formulário

```
Repository name:        bruno-bff-toolkit
Description:            Toolkit prático para Bruno + BFF Java/Spring Boot
Public:                 ✅ (deixe público)
Add a README.md:        ❌ (já temos)
Add .gitignore:         ❌ (já temos)
Choose a license:       MIT (já temos)
```

### 1.3 Clicar "Create repository"

---

## 💻 Passo 2: Inicializar Git Localmente

### 2.1 Abrir terminal na pasta do projeto

```bash
cd /caminho/para/bruno-repo
pwd  # Confirmar que está no lugar certo
```

### 2.2 Inicializar Git

```bash
# Verificar se já tem git
ls -la | grep .git

# Se não tiver, inicializar:
git init
```

### 2.3 Adicionar remote

**Substitua `SEU_USUARIO` pelo seu GitHub username:**

```bash
git remote add origin https://github.com/SEU_USUARIO/bruno-bff-toolkit.git
```

### 2.4 Confirmar

```bash
git remote -v
# Deve mostrar:
# origin  https://github.com/SEU_USUARIO/bruno-bff-toolkit.git (fetch)
# origin  https://github.com/SEU_USUARIO/bruno-bff-toolkit.git (push)
```

---

## 📤 Passo 3: Primeiro Commit e Push

### 3.1 Adicionar todos os arquivos

```bash
git add .
```

### 3.2 Verificar o que vai subir

```bash
git status
# Deve listar todos os arquivos .md, .html, .gitignore, LICENSE, etc
# NÃO deve listar .env (está em .gitignore)
```

### 3.3 Fazer commit

```bash
git commit -m "Initial commit: Bruno BFF Toolkit completo

- README.md com guia completo
- QUICK_START.md para começar rápido
- ORGANIZACAO.md com estrutura profissional
- FEATURES_FREE.md explicando o free
- Ferramentas HTML interativas (2)
- Exemplos de collections
- .gitignore configurado
- LICENSE MIT"
```

### 3.4 Fazer push

```bash
# Primeira vez precisa definir branch
git push -u origin main

# Ou se a branch padrão é main:
git branch -M main
git push -u origin main
```

**Pode pedir GitHub login.** Escolha autenticação por:
- ✅ Personal Access Token (recomendado)
- ✅ OAuth
- ✅ SSH key

---

## ✅ Passo 4: Verificar no GitHub

### 4.1 Ir para seu repositório

```
https://github.com/SEU_USUARIO/bruno-bff-toolkit
```

### 4.2 Conferir arquivos

Você deve ver:
- ✅ README.md (mostrando automaticamente)
- ✅ .gitignore
- ✅ LICENSE
- ✅ QUICK_START.md
- ✅ ORGANIZACAO.md
- ✅ FEATURES_FREE.md
- ✅ ferramentas/ (com HTMLs)
- ✅ exemplos/ (com .env.example)
- ✅ guias/ (pasta)

---

## 🔗 Passo 5: Compartilhar Link

### Seu URL público:

```
https://github.com/SEU_USUARIO/bruno-bff-toolkit
```

### Compartilhe com o time:

```bash
# No seu time/empresa, envie:
"Aqui está nosso toolkit Bruno: https://github.com/SEU_USUARIO/bruno-bff-toolkit"

# Cada pessoa faz:
git clone https://github.com/SEU_USUARIO/bruno-bff-toolkit.git
cd bruno-bff-toolkit
cp .env.example .env
# Edita .env
# Abre em Bruno
```

---

## 🔄 Passo 6: Adicionar Mais Conteúdo

### Quando quiser adicionar novo guia/exemplo:

```bash
# Criar novo arquivo
echo "# Novo Guia" > guias/06-Seu-Topico.md

# Adicionar
git add guias/06-Seu-Topico.md

# Commitar
git commit -m "Add: novo guia sobre seu tópico"

# Pushar
git push
```

---

## 🎁 Bônus: Adicionar Badge no README

No topo do `README.md`, adicione:

```markdown
[![GitHub](https://img.shields.io/badge/GitHub-bruno--bff--toolkit-blue)](https://github.com/SEU_USUARIO/bruno-bff-toolkit)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-1.0.0-brightgreen)]()
```

---

## ❓ Problemas Comuns

### "Permission denied (publickey)"

**Solução:**
```bash
# Usar HTTPS em vez de SSH
git remote set-url origin https://github.com/SEU_USUARIO/bruno-bff-toolkit.git
git push
```

### "fatal: could not read Username for 'github.com'"

**Solução:**
```bash
# Usar Personal Access Token (melhor que senha)
# 1. GitHub → Settings → Developer Settings → Personal Access Tokens
# 2. Generate new token (classic)
# 3. Marque: repo (all)
# 4. Copy token
# 5. Usar como senha no git push
```

### ".env foi commitado acidentalmente"

**Solução:**
```bash
# Remover do histórico
git rm --cached .env
git commit -m "Remove: .env do repositório (secrets)"
git push

# Editar .gitignore se não tiver
echo ".env" >> .gitignore
git add .gitignore
git commit -m "Add: .env ao gitignore"
git push
```

---

## 🚀 Pronto!

Seu toolkit está público e compartilhável!

### Próximos passos:

1. ✅ Compartilhe o link com o time
2. ✅ Eles clonam o repo
3. ✅ Configuram `.env` localmente
4. ✅ Abrem em Bruno
5. ✅ Começam a usar

---

## 📞 Suporte

Se tiver dúvidas com Git/GitHub:
- [GitHub Docs](https://docs.github.com/)
- [Git Tutorials](https://git-scm.com/doc)

---

**Parabéns! 🎉 Você tem um toolkit profissional no GitHub!**
