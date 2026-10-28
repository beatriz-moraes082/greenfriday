# Villa da Mata · 3 noites + jantar

Landing page da oferta do Sítio Villa da Mata (São Miguel dos Milagres, AL): reserve a partir de 3 noites e ganhe um jantar a dois no Bistrô.

No ar em: https://beatriz-moraes082.github.io/lp-villa-da-mata-3-noites/

- `index.html`: página única, sem build. Lenis (rolagem suave) vem do jsDelivr.
- `img/`: fotos do site da pousada em WebP, imagem de compartilhamento (`og-3-noites-jantar.jpg`, 1200×630) e ícones.
- `fonts/`: Marcellus e Figtree (Google Fonts, licença OFL), hospedadas aqui para não travar o carregamento.

## Reserva e rastreamento

A busca de datas abre o motor do Soufoco já com as datas (`villadamata.soufoco.com.br/search/AAAA-MM-DD/AAAA-MM-DD/adultos`), com mínimo de 3 noites. Os botões de WhatsApp vão para (82) 99317-9086 com a mensagem da oferta e as datas escolhidas.

A página carrega o GTM do site (`GTM-N87QTJHH`) e envia para o `dataLayer`:

| Evento | Quando | Campos |
|---|---|---|
| `clique_motor` | clique em "Ver disponibilidade" e links do motor | `oferta`, `origem`, `checkin`, `checkout` |
| `clique_whatsapp` | clique em qualquer botão de WhatsApp | `oferta`, `origem`, `checkin`, `checkout` |

Os acionadores e as tags de conversão (Google Ads, GA4, Meta) precisam ser criados no GTM, usando esses dois eventos personalizados.

## Regras da oferta (Green Friday, definidas em out/2026)

- A cada 3 diárias, um jantar para o casal no Bistrô (6 diárias, dois jantares).
- Vale para reservas feitas de 1º a 30/11/2026, só pelos canais diretos (site/motor próprio e WhatsApp). Não vale no Booking.
- Hospedagem em qualquer data do ano, todos os dias da semana, sem bloqueio de datas especiais (inclusive janeiro).
- Pagamento em até 6x no cartão.

## Pendências

- Trechos marcados com `A CONFIRMAR` no código: o que entra no jantar e se a oferta vale também para as suítes.
- A promoção precisa estar cadastrada no motor (Foco). Se a campanha tiver link ou cupom próprio, colocar no link do motor.
- A nota do Google (4,8 com 66 avaliações, em 28/10/2026) está escrita na página. Atualizar quando mudar.
- Se a página for para um subdomínio da pousada, trocar o endereço em `canonical`, `og:url`, `og:image` e no JSON-LD.

## Quando a oferta acabar (depois de 30/11/2026)

Escolher um dos dois:
1. Redirecionar a página para o site da pousada (no GitHub Pages: trocar o `index.html` por um com `<meta http-equiv="refresh" content="0; url=https://www.sitiovilladamata.com.br">` e `<link rel="canonical" href="https://www.sitiovilladamata.com.br">`).
2. Ou manter a página, mas com `<meta name="robots" content="noindex">` no `<head>` e um aviso de oferta encerrada.
