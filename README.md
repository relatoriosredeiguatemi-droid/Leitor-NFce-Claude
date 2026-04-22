# 📄 NFC-e Leitor SP

Leitor de QR Code de NFC-e SP com **scraping direto da Sefaz** — sem necessidade de API key, sem custo por consulta.

## Como funciona

1. O frontend lê o QR Code pela câmera (ou aceita URL colada)
2. Envia a URL para o backend (`/api/consultar`)
3. O backend busca a página da Sefaz SP com `node-fetch`
4. Faz o parse do HTML com `cheerio` e retorna JSON estruturado
5. O frontend exibe os dados organizados

**Nenhuma API externa paga é necessária.**

---

## 🚀 Deploy gratuito

### Vercel (recomendado)

```bash
npm i -g vercel
vercel --prod
```
Ou: importe o repositório em [vercel.com](https://vercel.com) → Deploy direto. Nenhuma variável de ambiente necessária.

---

### Render

1. [render.com](https://render.com) → **New Web Service**
2. Conecte o repositório GitHub
3. Configure:
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
4. Deploy ✅ — nenhuma env var necessária

---

### Railway

1. [railway.app](https://railway.app) → **New Project** → Deploy from GitHub
2. Railway detecta o `package.json` automaticamente
3. Deploy ✅

---

### Netlify

1. [netlify.com](https://netlify.com) → **Add new site** → Import from Git
2. O `netlify.toml` configura tudo automaticamente
3. Deploy ✅

---

## 💻 Rodar localmente

```bash
git clone https://github.com/seu-usuario/nfce-leitor-sp
cd nfce-leitor-sp
npm install
npm start
# Acesse http://localhost:3000
```

---

## 📁 Estrutura

```
nfce-leitor-sp/
├── api/
│   ├── server.js       # Express (Vercel/Render/Railway)
│   └── parser.js       # Parser HTML da NFC-e SP (cheerio)
├── netlify/
│   └── functions/
│       └── consultar.js # Serverless (Netlify)
├── public/
│   └── index.html      # Frontend completo
├── netlify.toml
├── vercel.json
└── package.json
```

---

## ⚠️ Observações

- URLs de QR Code da NFC-e expiram após algumas horas
- Funciona apenas com NFC-e do estado de SP
- Nenhum dado da nota é armazenado
