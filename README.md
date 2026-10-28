# Villa da Mata · Green Friday

Landing page da Green Friday do Sítio Villa da Mata (São Miguel dos Milagres, AL), com as três ofertas da campanha. O repositório manteve o nome da primeira versão (3 noites + jantar).

No ar em: https://beatriz-moraes082.github.io/lp-villa-da-mata-3-noites/

- `index.html`: página única, sem build. Lenis (rolagem suave) vem do jsDelivr.
- `img/`: fotos do site da pousada em WebP, imagem de compartilhamento (`og-3-noites-jantar.jpg`, 1200×630) e ícones.
- `fonts/`: Marcellus e Figtree (Google Fonts, licença OFL), hospedadas aqui para não travar o carregamento.

## Reserva e rastreamento

Todos os botões levam para o WhatsApp da pousada, (82) 99317-9086, com a mensagem da oferta e as datas escolhidas na busca. A página não leva para o motor de reservas.

A página carrega o GTM do site (`GTM-N87QTJHH`) e envia para o `dataLayer`:

| Evento | Quando | Campos |
|---|---|---|
| `clique_whatsapp` | clique em qualquer botão de WhatsApp | `oferta`, `origem`, `checkin`, `checkout` |

Os acionadores e as tags de conversão (Google Ads, GA4, Meta) precisam ser criados no GTM, usando esse evento personalizado.

## Regras da Green Friday (definidas em out/2026)

Reservas feitas de 1º a 30/11/2026, só pelos canais diretos (site/motor próprio e WhatsApp). Não vale no Booking. As ofertas não se somam: o cliente escolhe uma.

| Oferta | Condição | Hospedagem |
|---|---|---|
| Desconto progressivo | 2 diárias 15%, 3 diárias 20%, 4 ou mais 25% | maio a outubro (2027) |
| 3 diárias + jantar | a cada 3 diárias, um jantar para o casal | qualquer data |
| Espaço de eventos | 25% na locação do espaço | qualquer mês |

Todos os dias da semana, sem bloqueio de datas especiais (inclusive janeiro). Pagamento em até 6x.

A busca de datas exige no mínimo 2 noites e o resumo mostra qual oferta as datas permitem. O `dataLayer` recebe `oferta` = `desconto_progressivo`, `3_diarias_jantar`, `espaco_eventos` ou `green_friday` (botões gerais).

## Pendências

- Trecho marcado com `A CONFIRMAR` no código: o que entra no jantar.
- A nota do Google (4,8 com 66 avaliações, em 28/10/2026) está escrita na página. Atualizar quando mudar.
- Se a página for para um subdomínio da pousada, trocar o endereço em `canonical`, `og:url`, `og:image` e no JSON-LD.

## Quando a oferta acabar (depois de 30/11/2026)

Escolher um dos dois:
1. Redirecionar a página para o site da pousada (no GitHub Pages: trocar o `index.html` por um com `<meta http-equiv="refresh" content="0; url=https://www.sitiovilladamata.com.br">` e `<link rel="canonical" href="https://www.sitiovilladamata.com.br">`).
2. Ou manter a página, mas com `<meta name="robots" content="noindex">` no `<head>` e um aviso de oferta encerrada.
