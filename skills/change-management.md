# Skill: Gestão de Alterações

## Objetivo

Conduzir solicitações de mudança no SousaVet depois que INTENT, SPECs e Issues já tiverem sido definidas. Preservar a rastreabilidade entre solicitação, requisitos afetados, documentação, Issues e implementação.

Esta skill não substitui as SPECs nem autoriza o agente a decidir sozinho mudanças de escopo.

## Quando utilizar

Utilize esta skill quando o professor, gestor ou responsável solicitar:
- funcionalidade nova;
- alteração de comportamento especificado;
- mudança em campos, fluxos, permissões ou regras de negócio;
- alteração de arquitetura ou tecnologia;
- mudança que afete privacidade, segurança ou tratamento de dados clínicos.

Correções técnicas que não alterem o comportamento especificado seguem o fluxo normal da Issue.

## Procedimento obrigatório

### 1. Compreender a solicitação

Registre o pedido com as palavras do solicitante, sem ampliar seu significado. Se houver ambiguidade que impeça avaliar o impacto, faça perguntas objetivas.

### 2. Analisar impactos

Identifique:
- INTENT e SPECs afetadas;
- regras de negócio e fluxos impactados;
- telas, dados e permissões afetados;
- impactos de segurança, privacidade e auditoria;
- testes que precisam ser criados ou atualizados;
- Issues que precisam ser alteradas, divididas ou criadas;
- riscos de compatibilidade e migração de dados.

Não presuma decisões não documentadas. Marque como pendente o que depender de confirmação do professor ou gestor.

### 3. Apresentar proposta para decisão

Apresente:
- o que foi solicitado;
- como o sistema funciona atualmente segundo as SPECs;
- o que mudaria;
- alternativas relevantes;
- impactos, riscos e pendências;
- recomendação técnica, identificada como recomendação.

Aguarde aprovação explícita do responsável antes de alterar SPECs ou implementar mudança de escopo.

### 4. Registrar a alteração

Após aprovação, crie a próxima identificação sequencial `ALT-NNN` em `docs/REGISTRO_DE_ALTERACOES.md`, contendo:
- identificador e data;
- solicitante;
- descrição original;
- justificativa;
- decisão e responsável pela aprovação;
- SPECs, arquivos e Issues afetados;
- impactos, riscos e plano de validação.

Não invente data, solicitante ou aprovação. Se algum dado não estiver disponível, registre como pendente.

### 5. Atualizar a documentação

Atualize as SPECs afetadas e os demais documentos necessários. Preserve o histórico da decisão. Verifique se PLAN e Issues precisam ser atualizados.

A documentação deve deixar claro o comportamento esperado, as regras de negócio, os critérios de aceitação e os casos de teste.

### 6. Atualizar o GitHub

Quando houver acesso:
- atualize ou crie as Issues afetadas;
- mantenha referências à `ALT-NNN` e às SPECs;
- ajuste dependências e ordem de execução;
- não feche Issues automaticamente porque a documentação mudou.

Se não houver permissão para modificar o GitHub, prepare o conteúdo e informe o que precisa ser publicado. Nunca afirme que uma alteração remota foi realizada sem confirmação.

### 7. Implementar e validar

A implementação só começa depois da aprovação e da atualização documental. Siga `AGENTS.md` e as Issues atualizadas.

Execute os testes previstos e acrescente testes para os novos comportamentos e possíveis regressões. Registre os resultados na Issue.

## Restrições

- Não aprove mudanças em nome do professor ou gestor.
- Não altere silenciosamente uma SPEC aprovada.
- Não transforme sugestão do agente em requisito.
- Não remova requisitos existentes sem aprovação explícita.
- Não use dados clínicos reais em exemplos, testes, prompts ou commits.
- Mudanças em permissões, sigilo, dados clínicos ou envio de informações a serviços externos exigem aprovação explícita.
- Não implemente mudança de escopo antes de registrar a decisão e atualizar a documentação.

## Modelo de registro

Use este formato em `docs/REGISTRO_DE_ALTERACOES.md`:

```markdown
## ALT-NNN — Título resumido

- **Data:** AAAA-MM-DD ou Pendente
- **Solicitante:** nome ou Pendente
- **Status:** Proposta | Aprovada | Rejeitada | Implementada
- **Aprovador:** nome ou Pendente

### Solicitação
Descrição fiel do pedido.

### Justificativa
Motivo informado pelo solicitante.

### Impactos
- SPECs afetadas:
- Regras de negócio:
- Permissões e privacidade:
- Arquitetura e dados:
- Testes:
- Issues:

### Decisão
Decisão explícita e responsável pela decisão.

### Validação
Testes e evidências necessários para concluir a alteração.
```

## Relação com outras instruções

- `AGENTS.md` define regras gerais de desenvolvimento e aprendizagem.
- As SPECs definem o comportamento aprovado do produto.
- O PLAN organiza a sequência de entrega.
- As Issues representam unidades de trabalho.
- Esta skill controla mudanças sobre o escopo documentado.
