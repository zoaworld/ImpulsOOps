# ImpulsOOps – Landing Page

Landing page da agência ImpulsOOps. Deploy no Vercel com domínio GoDaddy.

## Configuração do Formulário (Formspree)

1. Cria uma conta em [formspree.io](https://formspree.io)
2. Cria um novo formulário e copia o ID (ex: `xeoaqgqg`)
3. No `index.html`, substitui `YOUR_FORM_ID` na linha do formulário:
   ```html
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
   por:
   ```html
   action="https://formspree.io/f/SEU_ID"
   ```

## Repositório Git (para deploy via Vercel)

Na pasta do projeto, executa:

```bash
git init
git add .
git commit -m "Landing page ImpulsOOps"
```

Depois cria um repositório no GitHub e faz push:

```bash
git remote add origin https://github.com/TEU_USER/ImpulsOOps.git
git branch -M main
git push -u origin main
```

## Deploy no Vercel

1. Vai a [vercel.com/new](https://vercel.com/new)
2. **Importar** repositório Git (GitHub) ou **Upload** da pasta (arrastar para a área de deploy)
3. Deploy automático → URL `*.vercel.app`

## Ligar Domínio GoDaddy

1. No Vercel: **Settings** > **Domains** > **Add** → `impulsops.pt`
2. No GoDaddy: **Meus Produtos** > domínio > **DNS**
3. Adiciona os registos indicados pelo Vercel:
   - **www:** CNAME → `cname.vercel-dns.com`
   - **Domínio raiz:** A record (IP indicado) ou usa nameservers Vercel

## Estrutura

```
ImpulsOOps/
├── index.html    # Landing page
├── .gitignore
├── README.md     # Este ficheiro
└── DEPLOY.md     # Instruções domínio GoDaddy
```
