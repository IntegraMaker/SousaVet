# SPEC-02 — Animais e fichas

**Status:** relações confirmadas no briefing. Formulários reais e conferência com a entrevista estão pendentes.

## Requisitos confirmados

- Um identificador geral persistente reúne o histórico do mesmo animal, inclusive em retornos.
- Um animal pode ter múltiplas fichas, gerais ou secundárias. As fichas e os exames secundários podem ter identificadores próprios.
- Uma ficha pode ter uma ou mais imagens. O banco guarda as referências às imagens protegidas.
- As associações devem preservar a integridade dos vínculos. Usar registros sintéticos.

## Pendências

- Confirmar formatos dos identificadores existentes, modelos, campos e regras de preenchimento a partir de amostras autorizadas.
- Confirmar o tratamento de situações com identificação ambígua ou ilegível antes de definir regras de reconciliação.

## Fluxo

Registrar um animal com identificador geral e vincular a ele as fichas encontradas. Ao adicionar uma página, selecionar a ficha correspondente e preservar seu vínculo no histórico do animal.

## Critérios de aceite

- A partir do identificador do animal, recuperar duas ou mais fichas do mesmo histórico sem incluir fichas de outro animal.
- Associar múltiplas páginas à mesma ficha. Uma gravação com vínculo inexistente é recusada.
