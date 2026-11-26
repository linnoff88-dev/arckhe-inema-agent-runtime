# Política

Quanto maior o impacto da açêo, mais o humano participa. O padrêo é **"prepara e pede"**.

## Níveis de autonomia

| Nível | O agente… |
|---|---|
| N0 | só conversa |
| N1 | prepara; o humano executa |
| N2 | executa depois de pedir, a cada vez |
| N3 | executa sozinho e avisa |
| N4 | executa sozinho, sem aviso |

## Teto por tipo de açêo

| Açêo | Teto | No Claude Code | No Codex |
|---|---|---|---|
| Ler arquivo, página, planilha | N4 | permitido | `-s read-only` |
| Criar/alterar arquivo do projeto | N3 | `acceptEdits` | `-s workspace-write` |
| Comando que altera o sistema | N2 | pede confirmaçêo | sem auto-aprovaçêo |
| Enviar (e-mail, mensagem, post, push) | N2 | pede confirmaçêo | sem auto-aprovaçêo |
| Gastar dinheiro ou crédito | N1 | bloqueado | nêo executar |
| Apagar dados / produçêo | N1 + backup | bloqueado (`rm -rf`) | nêo executar |

Uma permissêo "sempre permitir" **nunca** passa do teto da açêo.

O `.claude/settings.json` deste repo aplica os bloqueios básicos (`rm -rf`, `git push --force`, `git reset --hard`). Para o Codex, use os `-s` da tabela.

## Integraçêo

- Só ferramentas oficiais pela assinatura (Claude Code, Codex CLI).
- Nunca passe credencial de uma ferramenta para outra.
- Engenharia reversa é laboratório: anote em `LIMITES.md` e nêo use em produçêo.

## Aprendizado (propõe → aprova → incorpora)

O agente **nêo muda as próprias regras**. Ele acrescenta uma linha aqui; você decide.

| data | o que aconteceu (com evidência) | proposta (1 linha) | status: proposto / aprovado / recusado |
|---|---|---|---|

Aprovado → vira regra no `CLAUDE.md`/`AGENTS.md`. Falhas vêo em `FALHAS.md` (data | o que quebrou | menor correçêo | prompt ou infra) e bloqueios do ambiente em `LIMITES.md`.
