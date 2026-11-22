# PLAN — Sequência de trabalho

A Issue 001 é o primeiro trabalho do estudante. As demais Issues seguem a ordem sugerida abaixo. As dependências indicam quais entregas precisam estar disponíveis para começar cada tarefa.

| Issue | Entrega | SPEC | Dependências |
| --- | --- | --- | --- |
| 001 | Configuração do ambiente e inicialização do SousaVet | [SPEC-00](specs/SPEC-00-ambiente.md) | — |
| 002 | Iniciar e encerrar sessão | [SPEC-01](specs/SPEC-01-usuarios-permissoes.md) | 001 |
| 003 | Aplicar permissões no servidor | [SPEC-01](specs/SPEC-01-usuarios-permissoes.md) | 002 |
| 004 | Vincular animal, fichas e páginas | [SPEC-02](specs/SPEC-02-animais-fichas.md) | 003 |
| 005 | Capturar frente e verso e preservar originais | [SPEC-03](specs/SPEC-03-digitalizacao.md) | 003, 004 |
| 006 | Ajustar cantos e corrigir perspectiva | [SPEC-03](specs/SPEC-03-digitalizacao.md) | 005 |
| 007 | Cadastrar tipos sintéticos e classificar formulários | [SPEC-04](specs/SPEC-04-ocr-extracao.md) | 006 |
| 008 | Registrar transcrição assistida | [SPEC-04](specs/SPEC-04-ocr-extracao.md) | 007 |
| 009 | Revisar e corrigir transcrição | [SPEC-05](specs/SPEC-05-revisao-validacao.md) | 003, 008 |
| 010 | Validar a fidelidade da transcrição | [SPEC-05](specs/SPEC-05-revisao-validacao.md) | 009 |
| 011 | Consultar histórico e filtrar fichas | [SPEC-06](specs/SPEC-06-busca-consulta.md) | 003, 004, 010 |
| 012 | Verificar segurança, auditoria e integração da Fase 1 | [SPEC-01](specs/SPEC-01-usuarios-permissoes.md), [SPEC-03](specs/SPEC-03-digitalizacao.md), [SPEC-05](specs/SPEC-05-revisao-validacao.md) | 011 |

## Dependências externas

As tarefas do MVP usam dados e permissões sintéticos. Confirmar com o hospital os modelos e campos reais antes de consolidar a classificação, a extração, a revisão e os filtros de produção. Aplicar a matriz real de permissões após confirmação institucional. A escolha de OCR/IA, eventual envio de dados reais, retenção e infraestrutura definitiva seguem as pendências do [INTENT](INTENT.md) e a [gestão de alterações](../skills/change-management.md).

## Fluxo de trabalho por Issue

- **Backlog** — tarefa planejada, aguardando início ou dependência. Estado inicial das Issues 002 a 012.
- **Ready** — tarefa pronta para desenvolvimento. Estado inicial da Issue 001.
- **In Progress** — estudante implementando o escopo da Issue.
- **In Review** — estudante executando testes e concluindo a avaliação pedagógica.
- **Done** — critérios aceitos, testes executados, três perguntas e microdesafio concluídos e hashes registrados.

Seguir o [AGENTS.md](../AGENTS.md) e o [guia dos desafios](../desafios/README.md). O estudante pode fechar sua própria Issue ao concluir as validações técnica e pedagógica, sem aprovação individual do professor. Quando houver acesso ao Project, atualizar o status do card.
