# Guia de Deploy – ImpulsOOps

## 1. Deploy no Vercel

### Opção A: Com GitHub

1. Cria repositório no [GitHub](https://github.com/new) (ex: `ImpulsOOps`)
2. Na pasta do projeto:
   ```bash
   git init
   git add .
   git commit -m "Landing page ImpulsOOps"
   git remote add origin https://github.com/TEU_USER/ImpulsOOps.git
   git branch -M main
   git push -u origin main
   ```
3. Vai a [vercel.com/new](https://vercel.com/new)
4. **Import** → seleciona o repositório ImpulsOOps
5. **Deploy** (sem alterar configurações)
6. Obténs URL: `https://impulsoops-xxx.vercel.app`

### Opção B: Upload direto

1. Vai a [vercel.com/new](https://vercel.com/new)
2. Arrasta a pasta `ImpulsOOps` para a área de upload
3. Deploy automático

---

## 2. Ligar Domínio GoDaddy ao Vercel

### No Vercel

1. Abre o projeto ImpulsOOps no dashboard
2. **Settings** → **Domains** → **Add**
3. Escreve o domínio (ex: `impulsops.pt` ou `www.impulsops.pt`)
4. O Vercel mostra os registos DNS necessários

### No GoDaddy

1. **Meus Produtos** → clica no domínio → **DNS** ou **Gerir DNS**
2. Adiciona os registos indicados pelo Vercel:

| Tipo  | Nome | Valor                    |
|-------|------|--------------------------|
| CNAME | www  | cname.vercel-dns.com     |
| A     | @    | 76.76.21.21 (ou o IP indicado) |

**Nota:** O IP exato aparece no painel Vercel ao adicionar o domínio.

### Alternativa: Nameservers Vercel

Se preferires gerir o DNS no Vercel:

1. No GoDaddy: **Domínios** → **Gerir** → **Nameservers** → **Alterar**
2. Escolhe "Personalizado" e usa:
   - `ns1.vercel-dns.com`
   - `ns2.vercel-dns.com`
3. No Vercel, adiciona o domínio e configura os registos no painel Vercel

### Propagação

- DNS: 1–4 horas (até 48h em casos raros)
- SSL: automático no Vercel após propagação

---

## 3. Formspree (antes de ir a produção)

1. [formspree.io](https://formspree.io) → cria conta e formulário
2. Copia o ID do formulário
3. Em `index.html`, substitui `YOUR_FORM_ID` por esse ID na linha:
   ```html
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
4. Faz novo deploy no Vercel (ou push se usas Git)
