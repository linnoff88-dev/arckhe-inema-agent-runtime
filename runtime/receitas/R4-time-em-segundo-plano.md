# R4 · Time em segundo plano

**Para quê:** várias sessões do Claude trabalhando ao mesmo tempo, cada uma com nome, papel e modelo, e você acompanhando de um lugar só. É a versêo oficial do "Threads" que se via em vídeos de mods.
**Via:** CLI oficial (`claude --bg`, `claude agents`) · **Política:** cada sessêo segue a POLITICA; use `--permission-mode plan` para papéis que só leem.
**Pré:** Claude Code logado; pasta marcada como confiável · **Dificuldade:** média · **Tempo:** 15 min

Atençêo: cada sessêo consome a cota da assinatura. Comece pela R2, que roda numa sessêo só.

## 1. Marque a pasta como confiável (uma vez)

Abra `claude` na pasta e escolha **"Yes, I trust this folder"**. Sem isso, o `--bg` responde `Workspace not trusted`.

## 2. Solte as sessões

```bash
claude --bg --permission-mode plan --name revisor "Leia runtime/POLITICA.md e responda em uma linha qual é o teto de 'Enviar'."
claude --bg --model sonnet --name executor "Crie resumo.md com 3 linhas sobre o que é este kit."
```

Nêo use `-p` junto com `--bg`: o Claude recusa (`--bg and --print conflict`).

## 3. Acompanhe

```bash
node runtime/scripts/observar.mjs
```

**Prova:** aparece uma tabela com `id`, `tipo` = `background`, o nome que você deu e o estado (`working`, `idle`, `done`, `blocked`, `failed`).

| Comando | Faz |
|---|---|
| `claude logs <id>` | mostra a tela da sessêo |
| `claude attach <id>` | entra na sessêo para conversar |
| `claude stop <id>` | para a sessêo |
| `node runtime/scripts/observar.mjs --todas` | sessões de todas as pastas |

## 4. Junte os resultados

Cada sessêo grava em arquivo. Termine com uma sessêo "chefe" (ou a R2) que lê os arquivos e consolida.
