# INEMA Agent Runtime

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

[![INEMA Agent Runtime](guia/assets/banner.jpg)](https://inematds.github.io/inema-agent-runtime/guia/)

Kit copiÃ¡vel para fazer seus agentes de IA (Claude Code e Codex) **descobrirem, conectarem e usarem** as ferramentas que vocÃª jÃ¡ tem, com regras claras do que podem fazer sozinhos.

NÃ£o Ã© plataforma nem servidor. Ã‰ uma pasta `runtime/` com 4 arquivos de regras, scripts de diagnÃ³stico e verificaÃ§Ã£o, pontes, uma guarda e 7 receitas testadas. Funciona pela **assinatura** do Claude Code e/ou do Codex: nenhuma API paga Ã© prÃ©-requisito.

**Guia:** https://inematds.github.io/inema-agent-runtime/guia/

## Em 10 minutos

```bash
git clone https://github.com/inematds/inema-agent-runtime meu-projeto
cd meu-projeto
node runtime/scripts/doctor.mjs        # o que estÃ¡ instalado e logado
```

Depois abra `claude` (ou `codex`) nessa pasta e peÃ§a:

> Leia runtime/LEIA-ME.md e me ajude a preencher o CAPACIDADES.md para o meu trabalho.

## O que tem aqui

| Arquivo | Para quÃª |
|---|---|
| `runtime/LEIA-ME.md` | O ciclo e a escada de vias |
| `runtime/CAPACIDADES.md` | Mapa das ferramentas que o agente pode usar e por qual via |
| `runtime/POLITICA.md` | O que o agente faz sozinho, o que pede antes e o que nunca faz |
| `runtime/ROTEAMENTO.md` | Qual modelo para qual tarefa (economiza cota) |
| `runtime/scripts/` | `doctor` (diagnÃ³stico), `observar` (time em segundo plano), `verificar` (critÃ©rios de pronto) |
| `runtime/pontes/` | `codex-exec.sh` (Claude usa Codex) e `mcp-modelo/` (sistema sem API vira ferramenta) |
| `runtime/mods/` | `runtime-guarda` (colisÃ£o e raio, jÃ¡ ligada neste kit) e `runtime-painel` (opcional) |
| `AGENTS.md` / `CLAUDE.md` | Fazem o Codex e o Claude lerem as mesmas regras |
| `.claude/` | PolÃ­tica aplicada, time de 3 papÃ©is e guarda ligada |

## Receitas

| # | Receita | Via |
|---|---|---|
| R1 | [Claude usa o Codex](runtime/receitas/R1-claude-usa-codex.md) | CLI |
| R2 | [Time de trÃªs papÃ©is](runtime/receitas/R2-time-tres-papeis.md) | subagentes |
| R3 | [Ponte MCP para sistema sem API](runtime/receitas/R3-ponte-mcp-sistema-sem-api.md) | ponte local + MCP |
| R4 | [Time em segundo plano](runtime/receitas/R4-time-em-segundo-plano.md) | `claude --bg` |
| R5 | [Navegador com polÃ­tica](runtime/receitas/R5-navegador-com-politica.md) | uso do computador |
| R6 | [Agente longo com verificaÃ§Ã£o](runtime/receitas/R6-agente-longo-com-verificacao.md) | CLI + critÃ©rios |
| R7 | [Guarda e painel](runtime/receitas/R7-guarda-e-painel.md) | hooks e mods |

Cada receita tem uma seÃ§Ã£o **Prova**: o comando e o que tem de aparecer. As provas rodadas estÃ£o no [CHANGELOG](CHANGELOG.md).

## A ideia em uma frase

Antes de dizer "impossÃ­vel", o agente sobe a escada das vias de integraÃ§Ã£o â€” **API â†’ MCP â†’ CLI â†’ SDK â†’ uso do computador â†’ ponte local â†’ engenharia reversa (sÃ³ laboratÃ³rio)** â€” e usa sempre a mais estÃ¡vel que existir.

## Requisitos

- Node 18+ Â· Claude Code e/ou Codex CLI logados pela assinatura
- Linux ou Mac. Windows: use WSL.

LicenÃ§a MIT Â· Parte do ecossistema [INEMA.CLUB](https://inema.club)

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>