ï»¿# INEMA Agent Runtime

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ê°Å¸â¡Â§ê°Å¸â¡Â· [PortuguêÂªs](README.md) êÂ· ê°Å¸â¡Âºê°Å¸â¡Â¸ [English](README.en.md) êÂ· ê°Å¸â¡Âªê°Å¸â¡Â¸ [EspaêÂ±ol](README.es.md)**

[![INEMA Agent Runtime](guia/assets/banner.jpg)](https://inematds.github.io/inema-agent-runtime/guia/)

Kit copiêÂ¡vel para fazer seus agentes de IA (Claude Code e Codex) **descobrirem, conectarem e usarem** as ferramentas que vocêÂª jêÂ¡ tem, com regras claras do que podem fazer sozinhos.

NêÂ£o êÂ© plataforma nem servidor. êâ° uma pasta `runtime/` com 4 arquivos de regras, scripts de diagnêÂ³stico e verificaêÂ§êÂ£o, pontes, uma guarda e 7 receitas testadas. Funciona pela **assinatura** do Claude Code e/ou do Codex: nenhuma API paga êÂ© prêÂ©-requisito.

**Guia:** https://inematds.github.io/inema-agent-runtime/guia/

## Em 10 minutos

```bash
git clone https://github.com/inematds/inema-agent-runtime meu-projeto
cd meu-projeto
node runtime/scripts/doctor.mjs        # o que estêÂ¡ instalado e logado
```

Depois abra `claude` (ou `codex`) nessa pasta e peêÂ§a:

> Leia runtime/LEIA-ME.md e me ajude a preencher o CAPACIDADES.md para o meu trabalho.

## O que tem aqui

| Arquivo | Para quêÂª |
|---|---|
| `runtime/LEIA-ME.md` | O ciclo e a escada de vias |
| `runtime/CAPACIDADES.md` | Mapa das ferramentas que o agente pode usar e por qual via |
| `runtime/POLITICA.md` | O que o agente faz sozinho, o que pede antes e o que nunca faz |
| `runtime/ROTEAMENTO.md` | Qual modelo para qual tarefa (economiza cota) |
| `runtime/scripts/` | `doctor` (diagnêÂ³stico), `observar` (time em segundo plano), `verificar` (critêÂ©rios de pronto) |
| `runtime/pontes/` | `codex-exec.sh` (Claude usa Codex) e `mcp-modelo/` (sistema sem API vira ferramenta) |
| `runtime/mods/` | `runtime-guarda` (colisêÂ£o e raio, jêÂ¡ ligada neste kit) e `runtime-painel` (opcional) |
| `AGENTS.md` / `CLAUDE.md` | Fazem o Codex e o Claude lerem as mesmas regras |
| `.claude/` | PolêÂ­tica aplicada, time de 3 papêÂ©is e guarda ligada |

## Receitas

| # | Receita | Via |
|---|---|---|
| R1 | [Claude usa o Codex](runtime/receitas/R1-claude-usa-codex.md) | CLI |
| R2 | [Time de trêÂªs papêÂ©is](runtime/receitas/R2-time-tres-papeis.md) | subagentes |
| R3 | [Ponte MCP para sistema sem API](runtime/receitas/R3-ponte-mcp-sistema-sem-api.md) | ponte local + MCP |
| R4 | [Time em segundo plano](runtime/receitas/R4-time-em-segundo-plano.md) | `claude --bg` |
| R5 | [Navegador com polêÂ­tica](runtime/receitas/R5-navegador-com-politica.md) | uso do computador |
| R6 | [Agente longo com verificaêÂ§êÂ£o](runtime/receitas/R6-agente-longo-com-verificacao.md) | CLI + critêÂ©rios |
| R7 | [Guarda e painel](runtime/receitas/R7-guarda-e-painel.md) | hooks e mods |

Cada receita tem uma seêÂ§êÂ£o **Prova**: o comando e o que tem de aparecer. As provas rodadas estêÂ£o no [CHANGELOG](CHANGELOG.md).

## A ideia em uma frase

Antes de dizer "impossêÂ­vel", o agente sobe a escada das vias de integraêÂ§êÂ£o ê¢â¬â **API ê¢â â MCP ê¢â â CLI ê¢â â SDK ê¢â â uso do computador ê¢â â ponte local ê¢â â engenharia reversa (sêÂ³ laboratêÂ³rio)** ê¢â¬â e usa sempre a mais estêÂ¡vel que existir.

## Requisitos

- Node 18+ êÂ· Claude Code e/ou Codex CLI logados pela assinatura
- Linux ou Mac. Windows: use WSL.

LicenêÂ§a MIT êÂ· Parte do ecossistema [INEMA.CLUB](https://inema.club)

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>