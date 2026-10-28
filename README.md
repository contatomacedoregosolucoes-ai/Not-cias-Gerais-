# Notícias Gerais — resumos diários por e-mail

Todo dia por volta das 6h (Brasília), uma tarefa agendada do Claude acorda a sessão do Claude Code que montou este repositório.
Essa sessão roda o procedimento abaixo e envia 3 e-mails para contato.macedoregosolucoes@gmail.com pelo Gmail:

| E-mail | Instruções | Modelo |
|---|---|---|
| 📈 Economia & Política | `prompts/economia.md` | Sonnet |
| 🎬 Cinema & Famosos | `prompts/cinema.md` | Sonnet (o Haiku não achava notícias suficientes) |
| 🤖 Novidades de IA | `prompts/ia.md` | Sonnet |

Regras comuns (janela de 7 dias, sem repetir notícias, layout e envio): `prompts/comum.md`.
As notícias já enviadas ficam em `historico/`, para não se repetirem nos e-mails seguintes.

## Procedimento diário
1. Garantir que o repositório está atualizado neste branch (`git pull origin claude/resumos-diarios`).
2. Lançar em paralelo 3 subagentes (Agent tool), um por categoria, com o modelo da tabela, e o prompt:
   "Trabalhe em /home/user/Not-cias-Gerais-. Siga as instruções de prompts/<categoria>.md (que manda ler prompts/comum.md)."
3. Ao terminar, fazer commit de `historico/` e `git push -u origin claude/resumos-diarios`.
4. Se algum agente não conseguir enviar, enviar o HTML de `saida/<categoria>.html` pelo Gmail.
