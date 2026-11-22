# INTENT — SousaVet

## Objetivo

Digitalizar fichas veterinárias históricas impressas e manuscritas do Hospital Veterinário do Campus Sousa. Reunir fichas gerais e fichas secundárias sob o identificador persistente do animal, recuperar históricos em retornos e permitir consultas autorizadas. O SousaVet complementa o SimplesVet.

## Usuários

| Perfil | Direção confirmada no briefing |
| --- | --- |
| Professores e veterinários | Acesso amplo. Podem corrigir a transcrição ou encaminhá-la para revisão e validar sua fidelidade quando habilitados. |
| Secretaria | Acesso amplo para atividades autorizadas. |
| Estudantes auxiliares | Podem receber acesso compatível com atividades assistenciais. |
| Pesquisadores | Acesso mais restrito, preferencialmente a dados estruturados. |

A matriz final de ações, dados e perfis depende de confirmação do hospital. A implementação aplicará as permissões no servidor.

## Escopo

O MVP abrange autenticação e autorização, associação entre animais e múltiplas fichas, captura mobile-first/PWA de frente e verso, ajuste manual do enquadramento e da perspectiva, preservação das imagens originais, classificação do formulário, transcrição manuscrita assistida por OCR/IA, revisão humana, validação profissional e pesquisa com filtros autorizados. A detecção automática de bordas depende de viabilidade. A validação profissional atesta a fidelidade da transcrição ao original. Ultrassom, radiografia e outros exames de imagem ficam para uma segunda fase.

## Stack e proteção dos dados

Python, Flask, Jinja2, HTML, Bootstrap 5, HTMX e JavaScript próprio mínimo. PostgreSQL com SQLAlchemy e Alembic/Flask-Migrate. pytest, Docker e Docker Compose, com aplicação e banco em serviços separados e volume persistente. As imagens ficam em armazenamento de arquivos protegido, com referências no banco.

Usar dados sintéticos no desenvolvimento e nos testes. Proteger dados de tutores e fichas clínicas, aplicar controle de acesso no servidor, CSRF, validação de upload e auditoria. O uso de documentos reais em IA externa depende de autorização institucional expressa e avaliação de privacidade.

## Fontes e decisões pendentes

Esta versão consolida o briefing do professor e o AGENTS.md. A conferência das SPECs com a transcrição da entrevista “Chico Léo” permanece pendente.

- Modelos, campos e variações dos formulários reais.
- Matriz de permissões por perfil, ação e dado.
- Escolha de provedor de OCR/IA e autorização institucional para uso de dados reais.
- Política de retenção e infraestrutura definitiva.

Tratar hipóteses como propostas. Registrar decisões e mudanças conforme a [gestão de alterações](../skills/change-management.md).
