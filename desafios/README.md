# Desafios por Issue

Após a implementação e os testes, o Claude Code faz três perguntas conceituais, uma por vez, sobre o código efetivamente produzido. O estudante responde com suas palavras. Se necessário, o tutor oferece dicas progressivas e reapresenta uma pergunta equivalente.

O tutor prepara um único microdesafio com base no código da Issue, com duração-alvo de cinco minutos e tentativa inicial de até dez. Cria somente o enunciado e, se indispensável, arquivos iniciais mínimos. O estudante escreve a solução e o tutor pode orientar com dicas. Se a tarefa ultrapassar o tempo previsto, simplifique.

Antes do exercício, o tutor deve apresentar a instrução prevista no [AGENTS.md](../AGENTS.md#6-validação-pedagógica-obrigatória):

> Resolva este exercício exclusivamente na pasta `desafios/issue-NNN/`. Não modifique arquivos da aplicação principal.

Substitua `NNN` pelo número da Issue nos caminhos e commits. Use dados fictícios e mantenha o exercício isolado dos módulos, do banco da aplicação e do ambiente de produção.

Confira o diff e versione o exercício em um commit separado, `learn(issue-NNN): concluir desafio prático`, que contenha somente os arquivos de `desafios/issue-NNN/`. Registre na Issue os testes executados, os conceitos avaliados, as dificuldades, o resultado do microdesafio e os hashes da implementação, das correções aplicáveis e do aprendizado. O estudante pode fechar a própria Issue após a validação técnica e pedagógica.
