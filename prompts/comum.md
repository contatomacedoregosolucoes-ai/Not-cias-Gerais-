# Regras comuns a todos os resumos

Destinatário: contato.macedoregosolucoes@gmail.com

## Pesquisa
- Descubra a data de hoje com `TZ=America/Sao_Paulo date`.
- Use a ferramenta WebSearch (modo "standard"; carregue via ToolSearch se necessário), no máximo o número de buscas indicado no prompt da categoria.
- Inclua a data de hoje, "hoje", "esta semana" ou o mês/ano nas buscas para trazer notícias frescas.
- Se uma busca no modo "standard" vier fraca, desatualizada ou só com agregadores, refaça-a no modo "extended" (no máximo 2 buscas "extended" por e-mail).
- Varie as buscas por veículo/tema (ex.: incluir o nome do veículo ou da empresa) para achar a matéria original de cada fato.

## Links
- Cada notícia precisa do link da MATÉRIA ESPECÍFICA sobre aquele fato. Nunca use o mesmo link para duas notícias.
- Prefira a fonte original (veículo que apurou ou blog oficial da empresa) a agregadores e resumões; no máximo 2 notícias do mesmo veículo.

## Janela de tempo e repetição
- Use notícias dos ÚLTIMOS 7 DIAS, priorizando as mais recentes (últimas 24–48h primeiro).
- Leia o arquivo de histórico da categoria (`historico/<categoria>.md`). Ele lista as notícias já enviadas.
  NÃO repita nenhuma notícia que já esteja lá, nem o mesmo fato com outro link ou outro título.
  Exceção: um desdobramento realmente novo do mesmo assunto (ex.: "Copom decidiu" depois de "Copom vai decidir") pode entrar, deixando claro o que há de novo.
- Mostre a data de publicação de cada notícia na linha do link.

## Veracidade
- Use apenas URLs que apareceram de fato nos resultados da busca. Nunca invente links, números, benchmarks ou fatos.
- Se não tiver certeza de um dado, não o inclua. Melhor menos notícias do que notícias erradas.

## Escrita
- Português do Brasil, texto CORRIDO em parágrafos (sem listas com marcadores dentro das notícias), frases claras,
  termos técnicos explicados no próprio texto. Revise ortografia e acentuação.

## Layout HTML (estilos inline; COR e COR_CLARA definidas no prompt da categoria)
- Envoltório: `<div style="background:#f2f3f5;padding:24px 10px;font-family:Arial,Helvetica,sans-serif;"><div style="max-width:640px;margin:0 auto;background:#ffffff;border-radius:12px;overflow:hidden;"> ... </div></div>`
- Cabeçalho: `<div style="background:COR;color:#ffffff;padding:28px 28px 22px;"><div style="font-size:12px;letter-spacing:1.5px;text-transform:uppercase;opacity:0.85;">Resumo diário · [dia da semana, DD de mês de AAAA]</div><h1 style="margin:8px 0 0;font-size:26px;line-height:1.25;">TÍTULO DO E-MAIL</h1></div>`
- Corpo: `<div style="padding:8px 28px 24px;"> ... </div>`
- Título de seção: `<h2 style="font-size:20px;color:#111111;border-bottom:2px solid COR;padding-bottom:6px;margin:32px 0 12px;">`
- Subtítulo da notícia: `<h3 style="font-size:17px;color:COR;margin:20px 0 6px;line-height:1.35;">`
- Parágrafo: `<p style="font-size:15px;line-height:1.7;color:#333333;margin:0 0 10px;">` (no parágrafo de abertura use font-size:16px)
- Caixa de destaque: `<p style="background:COR_CLARA;border-left:4px solid COR;padding:10px 14px;margin:0 0 8px;font-size:14px;line-height:1.55;color:#333333;"><strong>RÓTULO:</strong> ...</p>`
- Link: `<p style="margin:0 0 22px;font-size:14px;"><a href="URL" style="color:COR;font-weight:bold;text-decoration:none;">Ler a notícia completa →</a> <span style="color:#888888;">· Fonte: VEÍCULO · DD/MM</span></p>`
- Tabela: `<table style="width:100%;border-collapse:collapse;font-size:14px;color:#333333;">`, cabeçalho com fundo COR_CLARA, células com padding:8px e border-bottom:1px solid #eeeeee.
- Rodapé: `<div style="padding:16px 28px;background:#f7f7f8;color:#888888;font-size:12px;text-align:center;line-height:1.5;">Resumo gerado automaticamente pelo Claude · cada notícia traz o link da fonte original</div>`
- Antes de enviar: todas as tags fechadas, nenhum link vazio, nada de Markdown (** ou #) no HTML.

## Envio e registro
1. Envie UM e-mail com a ferramenta `mcp__Gmail__send_message` (carregue via ToolSearch se necessário):
   to = ["contato.macedoregosolucoes@gmail.com"], subject = ASSUNTO + " – DD/MM/AAAA", htmlBody = o HTML,
   body = versão em texto puro organizada (títulos em MAIÚSCULAS, linha em branco entre notícias, link em linha própria, sem Markdown).
   Se a ferramenta de Gmail não existir, salve o HTML em `saida/<categoria>.html` e o texto em `saida/<categoria>.txt` e diga isso no final.
2. Depois de enviar, ACRESCENTE ao final de `historico/<categoria>.md` uma linha por notícia enviada, no formato:
   `AAAA-MM-DD | título curto | URL`
   Não apague linhas existentes.
3. Responda em no máximo 3 linhas: enviado ou não, quantas notícias, e qualquer problema.
