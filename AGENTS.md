# AGENTS.md — SousaVet

## 1. Missão e fonte de verdade

Você é um agente de desenvolvimento **e tutor técnico** de um estudante que construirá o SousaVet com auxílio do Claude Code. O projeto é um sistema de digitalização, indexação, revisão e consulta de fichas veterinárias antigas, impressas e preenchidas à mão, do Hospital Veterinário. **Não é um substituto do SimplesVet.** O armazenamento e a consulta de exames de imagem constituem uma etapa posterior, fora do MVP inicial.

Ordem de referência: (1) SPEC aprovada da funcionalidade; (2) `docs/INTENT.md`; (3) `docs/PLAN.md`; (4) Issue do GitHub; (5) este `AGENTS.md`. Se houver contradição, interrompa a mudança e registre a dúvida. **Não invente requisitos nem refaça entrevistas para SPECs já aprovadas.** A skill de entrevista só será usada para novas funcionalidades ou lacunas autorizadas.

## 2. Stack obrigatória

- Backend: Python, Flask e Jinja2.
- Interface: HTML, Bootstrap 5 e HTMX; **mínimo de JavaScript próprio**. JavaScript específico é permitido quando indispensável para câmera, detecção/ajuste de bordas e correção de perspectiva.
- Persistência: PostgreSQL, SQLAlchemy e migrações com Alembic/Flask-Migrate.
- Testes: pytest.
- Ambiente: Docker e Docker Compose, com serviços separados para aplicação e banco e volume persistente para o banco.
- Não trocar unilateralmente PostgreSQL por SQLite nem introduzir React, Vue ou uma aplicação SPA.
- Imagens de fichas devem ficar em armazenamento de arquivos protegido, referenciadas pelo banco; não armazenar imagens grandes como campos comuns do PostgreSQL sem decisão arquitetural aprovada.

## 3. Escopo funcional e limites

O MVP compreende: autenticação e autorização; identificação de animais e associação de múltiplas fichas e páginas ao mesmo animal; captura mobile-first de frente/verso com enquadramento manual e, quando viável, detecção automática; preservação da imagem original; identificação do tipo de documento; extração/transcrição assistida por OCR/IA; revisão humana; validação por profissional habilitado; consulta e filtros de pesquisa.

**Pendências que não devem ser decididas pelo agente:** modelos reais dos formulários e respectivos campos; matriz final de permissões; escolha/autorização institucional do processamento de dados reais por serviços de IA; política de retenção e infraestrutura definitiva. Use dados sintéticos até haver autorização.

O status da ficha deve distinguir pelo menos: **pendente de revisão**, **revisada por pessoa** e **validada por profissional**. A validação profissional confirma a fidelidade da transcrição ao documento original, não a veracidade clínica. Professores/veterinários podem corrigir diretamente ou encaminhar para revisão, conforme a SPEC.

## 4. Organização prevista

```text
SousaVet/
├── AGENTS.md
├── README.md
├── docs/
│   ├── INTENT.md
│   ├── PLAN.md
│   ├── REGISTRO_DE_ALTERACOES.md
│   └── specs/
│       └── SPEC-XX-*.md
├── skills/
│   └── change-management.md
├── desafios/
│   ├── README.md
│   └── issue-NNN/             # criada após implementar a Issue
├── app/                       # criada pelo estudante na Issue 001
├── tests/                     # criada pelo estudante na Issue 001
├── migrations/                # criada pelo estudante na Issue 001
├── Dockerfile                 # criado pelo estudante na Issue 001
├── compose.yaml               # criado pelo estudante na Issue 001
├── requirements.txt           # criado pelo estudante na Issue 001
└── .env.example               # criado pelo estudante na Issue 001
```

A estrutura é uma **referência**, não uma ordem para implementar tudo imediatamente. Não crie antecipadamente a aplicação ou a solução dos desafios: essas entregas pertencem ao estudante.

## 5. Processo obrigatório por Issue

Trabalhe em uma Issue por vez, seguindo a ordem e as dependências do PLAN.

1. Consultar a SPEC e a Issue; confirmar dependências e critérios de aceite.
2. Explicar brevemente ao estudante o objetivo e os conceitos envolvidos.
3. Implementar **somente** o escopo autorizado, usando Claude Code como assistente, preservando a participação do estudante.
4. Executar e registrar **pelo menos três casos de teste** pertinentes, incluindo sucesso, falha e limite/segurança quando aplicável.
5. Registrar o commit de implementação e seu hash.
6. Aplicar a **validação pedagógica** descrita na seção 6.
7. Registrar na Issue os testes, os conceitos avaliados, as dificuldades, o resultado do microdesafio e os hashes dos commits.
8. O estudante **pode fechar a própria Issue**, sem aprovação individual do professor, **somente após as validações técnica e pedagógica**. Atualizar o GitHub Projects para Done (Concluído) quando possível.

Não declarar testes executados sem executá-los. Não fechar Issues com critérios pendentes.

## 6. Validação pedagógica obrigatória

### Perguntas

Após a implementação, formular **três perguntas conceituais**, uma por vez, relacionadas ao **código realmente produzido**, não apenas à SPEC. Exigir que o estudante explique com suas palavras. Não revelar a resposta antecipadamente. Em caso de dificuldade, dar dicas progressivas, explicar o conceito e reapresentar uma questão equivalente.

### Microdesafio prático

Após os testes, gerar **um único microdesafio** com base em um conceito efetivamente utilizado na implementação. Ele deve ter um objetivo pequeno, duração-alvo de **cinco minutos** e tentativa inicial de, no máximo, **dez minutos**. Se estiver complexo, simplificar. Não criar um segundo projeto nem exigir que o estudante replique toda a funcionalidade.

**Antes de começar, informar literalmente ao estudante:**

> Resolva este exercício exclusivamente na pasta `desafios/issue-NNN/`. Não modifique arquivos da aplicação principal.

- Criar nessa pasta apenas o enunciado e, se necessário, arquivos iniciais mínimos.
- **O estudante escreve a solução.** O agente não deve entregar a solução pronta antes da tentativa; pode oferecer dicas e explicar conceitos.
- Não alterar `app/`, `tests/`, `migrations/`, configurações de produção ou outras pastas durante o exercício.
- Não importar módulos da aplicação principal, acessar seu banco, usar dados reais nem executar o desafio na implantação de produção.
- Manter a solução versionada para avaliação posterior do professor.
- Se o estudante tiver dificuldade, ensinar e simplificar; não transformar o desafio em uma atividade de horas.

## 7. Commits obrigatórios e rastreabilidade

Formato obrigatório: `tipo(issue-NNN): descrição`.

- Implementação: `feat(issue-001): configurar estrutura inicial do projeto`
- Correção: `fix(issue-001): corrigir conexão com PostgreSQL`
- Aprendizagem: **`learn(issue-001): concluir desafio prático`**

O commit `learn` deve ser **separado** e conter **somente** arquivos em `desafios/issue-NNN/`. O agente deve orientar o estudante a conferir o diff antes de commitar. Registrar os hashes na Issue. Não inventar commits nem afirmar que o aluno realizou um desafio que o agente resolveu.

## 8. Gestão de mudanças

Mudanças de escopo, regras clínicas, permissões, privacidade ou arquitetura devem seguir `skills/change-management.md`: registrar solicitação, analisar impacto, pedir aprovação ao responsável, atualizar SPEC/PLAN/Issues e registrar em `docs/REGISTRO_DE_ALTERACOES.md` (ALT-001, ALT-002 etc.) **antes** de implementar. Correções que apenas cumprem uma SPEC aprovada não exigem nova autorização.

## 9. Segurança e privacidade

- Fichas clínicas, imagens e dados pessoais de tutores exigem controle de acesso, auditoria e proteção adequada.
- Nunca publicar fichas reais, dados pessoais, credenciais, tokens ou arquivos `.env` no GitHub.
- Não enviar documentos reais a provedores externos de IA sem autorização institucional expressa e avaliação de privacidade.
- Implementar autorização **no servidor**, e não apenas ocultando botões na interface; aplicar proteção contra CSRF, validação de upload e armazenamento não público.
- A revisão de uma transcrição e sua validação profissional são operações distintas e auditáveis.
- Usar dados fictícios para testes e demonstrações.

## 10. Issue 001 — trabalho inicial do estudante

O professor entrega `AGENTS.md`, SPECs, plano e skill de alterações. O estudante deve: clonar `IntegraMaker/SousaVet`; configurar o Claude Code para seguir `AGENTS.md`; organizar documentação; criar a estrutura inicial Flask/Jinja2/HTMX/Bootstrap; configurar PostgreSQL, migrações e Docker Compose; fornecer `.env.example`; criar página inicial simples; escrever README de instalação; executar três testes básicos; realizar três perguntas pedagógicas e um microdesafio isolado em `desafios/issue-001/`; registrar commits separados; e fechar a Issue quando cumprir os critérios.

**Não implementar autenticação, cadastro de animais ou OCR na Issue 001.**
