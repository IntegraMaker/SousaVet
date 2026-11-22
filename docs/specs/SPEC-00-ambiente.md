# SPEC-00 — Ambiente de desenvolvimento

## Requisitos confirmados

- O estudante clona `IntegraMaker/SousaVet` e configura o Claude Code para carregar e seguir o AGENTS.md.
- A estrutura inicial inclui `app/`, `tests/`, `migrations/`, `Dockerfile`, `compose.yaml`, `requirements.txt` e `.env.example`.
- Flask renderiza uma página inicial simples com Jinja2, Bootstrap 5 e HTMX. Docker Compose executa aplicação e PostgreSQL em serviços separados, com volume persistente para o banco.
- SQLAlchemy e Alembic/Flask-Migrate conectam e preparam o banco. O estudante documenta instalação, migrações e testes no README.
- Credenciais locais ficam fora do Git. A Issue 001 cobre o ambiente e a estrutura inicial.

## Critérios de aceite

1. Uma instalação limpa segue o README, sobe os serviços, executa o fluxo de migrações e abre a página inicial.
2. O Claude Code demonstra que leu as regras do AGENTS.md. Os exemplos de configuração usam valores fictícios.
3. O estudante registra o resultado dos três testes da Issue 001 e completa o fluxo pedagógico do AGENTS.md.
