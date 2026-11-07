# ovenplatform.com.br

Site institucional estático do Oven Platform (HTML + CSS, sem build).

- `index.html` — apresentação do produto
- `privacidade.html` — política de privacidade (LGPD)
- `CNAME` — domínio customizado para o GitHub Pages

## Rodar localmente

```bash
python3 -m http.server 8765
```

## Publicar no GitHub Pages (gratuito, HTTPS incluso)

1. Criar o repositório público e enviar:
   ```bash
   gh repo create ovenplatform-site --public --source . --push
   ```
2. Ativar o Pages pela branch `main`, pasta raiz:
   ```bash
   gh api -X POST repos/{owner}/ovenplatform-site/pages -f "source[branch]=main" -f "source[path]=/"
   ```
3. No Registro.br (DNS de `ovenplatform.com.br`):
   - 4 registros `A` no domínio raiz: `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - `CNAME` de `www` para `<usuario-github>.github.io`
4. Depois que o DNS propagar, em *Settings → Pages*, marcar **Enforce HTTPS**.

## E-mail contato@ovenplatform.com.br

O site só usa `mailto:`; a caixa precisa de um provedor com registros `MX` no mesmo DNS.
Opção gratuita com envio e recebimento: Zoho Mail (plano Forever Free, 1 domínio).
