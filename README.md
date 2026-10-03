# Plena-Lab | site institucional

Redesign do site da **Plena-Lab Indústria e Comércio de Vidrarias para Laboratório**
(substitui o site atual em `plena-lab.com.br`, feito em Mobirise 4).

Site estático, uma única página, sem build e sem dependências: `index.html` + `assets/`.

## Rodar localmente

```bash
python3 -m http.server 4173
```

Depois abra <http://localhost:4173>.

## Publicar

Como é HTML estático, basta subir `index.html` e a pasta `assets/` para a raiz do
domínio: servidor atual (Locaweb), Netlify, Vercel, Cloudflare Pages ou GitHub Pages.
Nada precisa ser compilado.

## Estrutura da página

| Seção | Conteúdo |
|---|---|
| Hero | Posicionamento + CTAs para loja e orçamento |
| Números | 25+ anos, 10.000+ clientes, 280+ categorias, 9 linhas |
| Linhas | 9 cards com link direto para a categoria na `lojaplenalab.com.br` |
| Fabricação | Fábrica, oficina sob desenho, aferição ISO, serigrafia, embalagem, laboratório |
| Segmentos | 8 setores atendidos, cada um ancorado em produtos reais do catálogo |
| Como comprar | Loja on-line (Pix 5%) vs. venda consultiva / licitação |
| Time | 7 pessoas, com e-mail e WhatsApp individuais |
| FAQ | 9 perguntas em `<details>` (abre sem JavaScript) |
| Contato | Formulário que monta a mensagem e abre o WhatsApp, + dados completos |

## Decisões técnicas

- **Sem backend.** O formulário não envia nada para servidor nenhum: ele monta o texto
  e abre `wa.me` com a mensagem pronta (e o botão "Prefiro por e-mail" monta um `mailto:`
  equivalente). Zero custo de infra e zero dado armazenado.
- **Tipografia:** DM Sans (Google Fonts), com fallback de sistema.
- **Acessibilidade:** skip link, foco visível, `aria-*` no menu mobile, alt em todas as
  imagens e respeito a `prefers-reduced-motion`.
- **SEO:** title/description, Open Graph e JSON-LD (`Manufacturer`) com endereço,
  telefone e horário.
- **Performance:** ~490 KB de imagens no total, `loading="lazy"` abaixo da dobra,
  CSS e JS inline (um único request de HTML).

## Conteúdo: de onde veio

Todo o texto factual saiu dos sites atuais da empresa (`plena-lab.com.br` e
`lojaplenalab.com.br`): história, aferição ISO, oficina, serigrafia, embalagem,
laboratório, time, endereço, telefones, e-mails e categorias de produto.
As fotos de produto são as da própria loja.

## Pontos a confirmar antes de publicar

- **Horário de atendimento:** o site institucional antigo diz 8h às 18h e a loja diz
  8h às 17h30. Aqui está 8h às 17h30 (o dado mais recente, da loja). Ajustar se necessário.
- **CNPJ / Inscrição Estadual:** não constam em nenhum dos sites atuais, então não foram
  incluídos no rodapé. Se quiser exibir, é só acrescentar.
- **Favicon:** usa `assets/img/logo-azul.png` (300x100). Vale gerar um quadrado de 512x512.
- **Foto do time:** hoje os cards usam as iniciais. Com fotos reais a seção ganha muito.
