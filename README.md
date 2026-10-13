# Irineu

Consultor financeiro pessoal que funciona como uma ligação: você conta seus gastos falando, ele anota, separa o que é fixo, variável e parcelado, e pergunta o que não entendeu.

## Como o projeto está organizado

| Arquivo | O que faz |
|---|---|
| `docs/index.html` | O app inteiro: telas, visual (CSS) e lógica (JavaScript) num arquivo só. |
| `docs/manifest.webmanifest` | A "carteira de identidade" do app: nome, ícone e cores. É o que faz o Chrome oferecer **Instalar app**. |
| `docs/sw.js` | O *service worker*: guarda uma cópia do app no celular pra ele abrir rápido e até sem internet. |
| `docs/icon-*.png`, `docs/icon.svg` | Os ícones da tela inicial. |

## Onde ficam as coisas

- **Seus dados** (renda, contas, lançamentos) ficam só no seu celular, no armazenamento do Chrome. Use **Seu mês > Baixar backup** de vez em quando.
- **A chave da API** também fica só no celular. Ela nunca vai pro código.
- **A inteligência** vem da API do Claude (modelo Haiku, o mais rápido e barato), chamada direto do celular com a sua chave.
- **O microfone e a voz** são os do próprio Chrome: reconhecimento de voz pra te ouvir e a voz do Google pra falar.

## Como uma mudança chega no seu celular

1. O código é alterado e salvo aqui no GitHub (um *commit*).
2. O GitHub Pages publica a pasta `docs/` sozinho, em alguns minutos.
3. Na próxima vez que você abre o app com internet, ele já pega a versão nova.

## Economia de crédito

- Gasto simples ("42 no mercado no débito do Santander") é lido pelo próprio app, sem IA.
- Perguntas comuns ("quanto posso gastar por dia?") são calculadas pelo app.
- Na ligação, falas seguidas vão juntas numa chamada só, e a IA recebe só um resumo curto do que já foi anotado.
- Responder as dúvidas do Irineu pelos botões não usa IA.
