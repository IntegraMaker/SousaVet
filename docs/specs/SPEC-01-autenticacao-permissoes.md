# SPEC-01 — Autenticação e permissões

**Status:** requisitos consolidados a partir do briefing. A matriz final e a conferência com a entrevista estão pendentes.

## Requisitos confirmados

- Identificar o usuário antes de permitir acesso a fichas, imagens e transcrições.
- Aplicar permissões configuráveis no servidor, inclusive em rotas chamadas pelo HTMX e no acesso a imagens. Proteger operações de escrita contra CSRF.
- A direção para os perfis consta no [INTENT](../INTENT.md#usuários). Usar perfis e contas sintéticos para testar o mecanismo.

## Pendências

- Confirmar a matriz de permissões com o hospital, incluindo quem pode ver, corrigir, encaminhar, revisar e validar fichas.
- A especificação registra a necessidade de autenticação. Detalhes do acesso institucional que não constam no briefing permanecem em aberto.

## Critérios de aceite

- Uma conta sintética autenticada acessa uma operação de acordo com a permissão de teste.
- Sessões ausentes ou encerradas e permissões insuficientes são barradas pelo servidor. Uma escrita sem CSRF válido é recusada.
