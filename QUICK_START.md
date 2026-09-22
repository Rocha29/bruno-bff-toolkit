# ⚡ Quick Start (5 minutos)

Comece agora mesmo. Zero complicação.

---

## 📦 Passo 1: Baixar Bruno

👉 **https://www.usebruno.com/downloads**

Escolha seu SO (Mac, Windows, Linux) e instale.

---

## 📂 Passo 2: Clonar Este Repositório

```bash
git clone https://github.com/SEU_USUARIO/bruno-bff-toolkit.git
cd bruno-bff-toolkit
```

---

## ⚙️ Passo 3: Configurar Variáveis

### 3.1 Copiar `.env.example` → `.env`

```bash
cp .env.example .env
```

### 3.2 Editar `.env` com suas credenciais

```bash
# Abra em seu editor favorito
nano .env
# ou
code .env
```

### 3.3 Preencher valores

```env
# Seu STS
STS_URL=https://sts.seu-dominio.local
STS_CLIENT_ID=seu-client-id-real
STS_CLIENT_SECRET=seu-client-secret-real

# Seus endpoints
GATEWAY_URL=http://localhost:9090
```

**⚠️ IMPORTANTE:** Nunca commita `.env` real no Git!

---

## 🚀 Passo 4: Abrir em Bruno

1. Abra Bruno (aplicação instalada)
2. Clique: **File → Open Collection**
3. Selecione pasta: `bruno-bff-toolkit/.bruno/collections/auth/`
4. ✅ Collection carregada!

---

## ✅ Passo 5: Testar Primeira Request

1. Na sidebar esquerda, clique em: **Auth → STS-Token**
2. Veja a aba **Pre-request** (já tem código de cache)
3. Clique botão **Send** (ou Ctrl+Enter)
4. Em **Response**, você verá:
   ```json
   {
     "access_token": "eyJ0eXAiOiJKV1Q...",
     "expires_in": 3600
   }
   ```

✅ **Token cacheado automaticamente!**

---

## 🔗 Passo 6: Encadear Requests (Bônus)

1. Vá para: **Pagamentos → Tributos → Consultar**
2. Clique **Send**
3. Em **Test**, veja código que já faz:
   ```javascript
   bru.setNextRequest('Validar-Tributo')
   ```
4. Próximo request executa **automaticamente**

---

## 📚 Próximos Passos

### Para Entender Melhor

- 📖 [ORGANIZACAO.md](./ORGANIZACAO.md) — Como organizar collections
- 📖 [FEATURES_FREE.md](./FEATURES_FREE.md) — O que usar do free
- 📖 [guias/](./guias/) — Documentação detalhada

### Ferramentas Interativas

Abra em navegador (offline):
- 🎯 **[bruno-speed-start.html](./ferramentas/bruno-speed-start.html)** — Para iniciantes
- 🛠️ **[bruno-toolkit.html](./ferramentas/bruno-toolkit.html)** — Suite completa

### Exemplos

- 📁 **[exemplos/colecao-bff-tributos/](./exemplos/colecao-bff-tributos/)** — Collection completa pronta

---

## ⚠️ Troubleshooting Rápido

### "Token não está sendo usado"

❌ Problema: Header Authorization está vazio

✅ Solução:
1. Certifique-se que executou **STS-Token** PRIMEIRO
2. Verifique se header tem: `Authorization: Bearer {{ access_token }}`
3. Rode novamente

### "Request não encadeia"

❌ Problema: bru.setNextRequest() não funciona

✅ Solução:
1. Verifique se está usando **Collection Runner** (botão Play)
2. O nome do request está digitado **exatamente igual**?
3. Veja console (F12) para erros

### "Salvo em Bruno, mas não apareceu no Git"

❌ Problema: Mudanças não sincronizaram

✅ Solução:
```bash
git status  # Ver mudanças
git add .
git commit -m "Update: descrição"
git push
```

---

## 🎁 Dicas Rápidas

### Atalhos Importantes

```
Ctrl+Enter     → Enviar request
Ctrl+D         → Duplicar request
Ctrl+Shift+E   → Abrir Collection Runner
F12            → Abrir Console (debug)
Ctrl+K         → Buscar request
```

### Variáveis Dinâmicas (Copiar & Colar)

```
{{ $randomUUID }}       // ID único
{{ $timestamp }}        // Unix timestamp
{{ $isoTimestamp }}     // ISO format
{{ $randomInt }}        // Número aleatório
{{ $date }}             // Data (YYYY-MM-DD)
```

### Headers Padrão

```
Authorization: Bearer {{ access_token }}
Content-Type: application/json
X-Request-ID: {{ $randomUUID }}
X-Timestamp: {{ $timestamp }}
```

---

## ❓ FAQ

**P: Preciso de Bruno Pro?**  
R: Não. Tudo que você precisa está no FREE.

**P: Como atualizar a collection?**  
R: `git pull` no terminal. Bruno recarrega automaticamente.

**P: Posso compartilhar com meu time?**  
R: Sim! Faça push pro GitHub, time clona e abre. Pronto.

**P: E se tiver secrets?**  
R: Use `.env.local` (gitignored). Template em `.env.example`.

---

## 🚀 Você Está Pronto!

Agora:

1. ✅ Bruno instalado
2. ✅ Collection carregada
3. ✅ Variáveis configuradas
4. ✅ STS Token funcionando
5. ✅ Fluxos encadeados

**Próximo passo:** Explore outras requests, crie suas próprias, compartilhe no Git.

**Dúvidas?** Ver [README.md](./README.md) ou [ORGANIZACAO.md](./ORGANIZACAO.md)

---

**Happy coding! 🎉**
