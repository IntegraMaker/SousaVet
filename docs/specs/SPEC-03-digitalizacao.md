# SPEC-03 — Captura e digitalização

**Status:** fluxo básico confirmado no briefing. Critérios operacionais e conferência com a entrevista estão pendentes.

## Requisitos confirmados

- Capturar fichas em interface mobile-first/PWA e associar frente e verso, quando disponíveis, à mesma ficha.
- Validar o upload no servidor e armazenar a imagem original em área protegida.
- Permitir ajuste manual dos cantos e correção de perspectiva. Gravar a versão ajustada preservando o original e seu vínculo.
- Restringir o JavaScript próprio às operações que o exigem, como câmera e transformação de imagem.

## Hipóteses e pendências

- Detecção automática de bordas depende de viabilidade. O ajuste manual é o fluxo de referência.
- Confirmar formatos, limites de upload e cenários de captura com amostras autorizadas. Configurações de teste usam imagens sintéticas.

## Fluxo

Selecionar uma ficha e capturar ou enviar suas imagens. O servidor valida os arquivos e grava os originais sob controle de acesso. O operador pode ajustar os cantos de cada página e consultar a versão corrigida vinculada ao original.

## Critérios de aceite

- Capturar frente e verso de uma ficha sintética e recuperar ambos os originais com acesso autorizado.
- Corrigir a perspectiva de uma página sintética e verificar que o original permanece íntegro. Arquivo inválido é recusado.
