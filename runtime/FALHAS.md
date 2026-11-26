# Falhas

| data | o que quebrou | menor correçêo | prompt \| infra |
|---|---|---|---|
| 2026-10-05 | `doctor.mjs` dizia "codex sem login" com o Codex logado | ler stdout **e** stderr (`codex login status` responde no stderr) | infra |
