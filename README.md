# Pezão Imóveis

Site da Pezão Imóveis, imobiliária de Itapuranga - GO há mais de 30 anos
(Rua 45, nº 859, Centro). Compra, venda, avaliação e locação de imóveis urbanos e rurais.

## O que tem aqui

| Pasta / arquivo | O que é |
| --- | --- |
| `index.html` | O site (imóveis com galeria de fotos, sobre, contato pelo WhatsApp) e o painel. |
| `dados.json` | Todo o conteúdo do site: imóveis, preços, fotos, contatos, endereço e textos. |
| `fotos/` | Fotos dos imóveis. |
| `logo.png` | Logomarca. |
| `api/` | Funções do painel na Vercel (login, salvar e enviar fotos). |

## Painel da imobiliária (na Vercel)

O site tem um painel com usuário e senha (link "Painel da imobiliária" no rodapé, ou o
endereço do site com `/#painel` no final). Nele você edita imóveis, preços, fotos, WhatsApp,
corretor, endereço e textos. Ao salvar, o painel grava aqui no GitHub e a Vercel publica o
site de novo sozinha, em cerca de 1 minuto.

O painel só funciona na Vercel. No GitHub Pages o site aparece normal, mas o painel fica desligado.

### Como configurar a Vercel

1. Entre em https://vercel.com com a sua conta do GitHub.
2. Clique em **Add New → Project**, escolha **Pezao_Imobiliaria** e clique em **Deploy**.
3. No projeto, abra **Settings → Environment Variables** e cadastre:

| Nome | O que colocar |
| --- | --- |
| `ADMIN_USER` | O usuário do painel (ex.: `pezao`). |
| `ADMIN_PASSWORD` | A senha do painel. |
| `SESSION_SECRET` | Um texto longo e aleatório (40 letras e números quaisquer). |
| `GITHUB_TOKEN` | Um token do GitHub com permissão de escrever neste repositório (veja abaixo). |

4. Vá em **Deployments**, clique nos três pontinhos do último e em **Redeploy**.

**Como criar o `GITHUB_TOKEN`:** no GitHub, abra **Settings → Developer settings →
Personal access tokens → Fine-grained tokens → Generate new token**. Em **Repository access**
escolha **Only select repositories** e marque **Pezao_Imobiliaria**. Em **Permissions → Contents**
escolha **Read and write**. Gere o token, copie e cole na Vercel.

Para trocar usuário ou senha, mude `ADMIN_USER` e `ADMIN_PASSWORD` na Vercel e faça Redeploy.

## Editar sem o painel

Também dá para abrir `dados.json` aqui no GitHub, clicar no lápis (Editar) e mudar o conteúdo.
Fotos novas vão na pasta `fotos/`, com o caminho na lista `fotos` do imóvel
(ex.: `fotos/casa-nova-1.jpg`). Deixe `preco` em 0 para mostrar "Sob consulta" e use
`"oculto": true` para esconder um imóvel vendido.
