# SPEC-06 — Pesquisa e consulta

**Status:** objetivo de consulta e exemplos de filtros confirmados. Campos, permissões e conferência com a entrevista estão pendentes.

## Requisitos confirmados

- Permitir recuperar o histórico de fichas de um animal e pesquisar dados estruturados autorizados.
- O briefing indica diagnóstico, sexo, idade e período como exemplos de filtros úteis para o hospital.
- Aplicar permissões no servidor à lista de resultados, aos detalhes e aos originais. O acesso de pesquisadores é mais restrito e preferencialmente voltado aos dados estruturados.

## Pendências

- Confirmar campos e significados dos filtros nos formulários reais, inclusive a data que define o período e a referência para idade.
- Confirmar visibilidade por perfil e estado da ficha, além de eventuais regras de desidentificação.

## Critérios de aceite

- Consultar um histórico sintético e aplicar filtros sobre campos de teste com resultados reproduzíveis.
- Consulta sem correspondência retorna resultado vazio. Registro protegido não aparece na busca e não fica acessível por URL direta ao usuário sem permissão.
