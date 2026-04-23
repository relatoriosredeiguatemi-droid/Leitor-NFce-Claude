# NFC-e Leitor SP

Lê QR Code de NFC-e SP e extrai dados via scraping direto da Sefaz. **Sem API key. Sem custo.**

## Deploy no Vercel (recomendado)

### Opção A — Via GitHub (mais fácil)
1. Crie um repositório no GitHub e suba os arquivos
2. Acesse [vercel.com](https://vercel.com) → **Add New Project**
3. Importe o repositório → clique **Deploy**
4. Pronto ✅ — nenhuma configuração necessária

### Opção B — Via CLI
```bash
npm i -g vercel
vercel --prod
```

## Estrutura do projeto

```
nfce-leitor-sp/
├── api/
│   └── consultar.js   # Função serverless (rota POST /api/consultar)
├── public/
│   └── index.html     # Frontend completo
├── package.json
├── vercel.json
└── .gitignore
```

O Vercel detecta automaticamente:
- `api/*.js` → funções serverless
- `public/` → arquivos estáticos

## Rodar localmente

```bash
npm install
npx vercel dev
# Acesse http://localhost:3000
```

## Outros serviços gratuitos

### Netlify
Adicione o arquivo `netlify/functions/consultar.js` (adapte para o formato de handler do Netlify) e o `netlify.toml`.

### Render / Railway
Use o `server.js` com Express — rode como Web Service com `npm start`.
