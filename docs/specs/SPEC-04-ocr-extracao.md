# SPEC-04 — Classificação, OCR e transcrição

**Status:** assistência por OCR/IA confirmada no briefing. Catálogo, autorização e conferência com a entrevista estão pendentes.

## Requisitos confirmados

- Identificar o tipo do formulário antes de organizar a extração. Trabalhar com tipos sintéticos enquanto os modelos históricos não forem analisados.
- Distinguir extração pendente e transcrição pendente de revisão. Associar a sugestão de transcrição ao documento de origem.
- Encaminhar a sugestão para revisão humana. Uma extração sem resultado não equivale a uma transcrição nem a uma validação.
- Usar dados sintéticos e um substituto de OCR/IA nos testes. Uso de documentos reais em serviços externos depende de autorização institucional expressa e avaliação de privacidade.

## Pendências

- Catálogo dos formulários, campos por tipo e amostras manuscritas autorizadas.
- Escolha do provedor ou processamento local e critérios de avaliação da transcrição.

## Fluxo

Cadastrar tipos de teste e associar o tipo reconhecido ao documento. Processar a extração simulada e vincular o resultado ao original. Disponibilizar o texto sugerido para revisão humana.

## Critérios de aceite

- Um formulário sintético reconhecido recebe a referência ao tipo; um tipo desconhecido não é atribuído arbitrariamente.
- Uma extração simulada gera sugestão ligada à origem e pendente de revisão. Uma falha preserva a origem e não marca o material como revisado ou validado.
