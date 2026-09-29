Atue como um especialista em N8N.

Crie uma automação para organizar e acompanhar solicitações de tarefas recebidas por uma pequena equipe, centralizando as informações e facilitando o acompanhamento dos responsáveis e prazos.

Público:
Pequenas empresas e equipes que precisam organizar tarefas e acompanhar demandas sem depender de controles manuais.

Ferramentas envolvidas:
N8N, Google Sheets e e-mail.

Fluxo:
1. Receber uma nova solicitação por e-mail.
2. Identificar as informações principais da solicitação, como título, descrição, solicitante, prioridade e prazo, quando disponíveis.
3. Registrar a solicitação em uma planilha do Google Sheets.
4. Gerar um identificador único para a tarefa.
5. Enviar uma confirmação por e-mail ao solicitante informando que a demanda foi registrada.
6. Quando a tarefa estiver próxima do prazo, verificar seu status na planilha.
7. Enviar um lembrete ao responsável caso a tarefa ainda esteja pendente.
8. Atualizar a planilha com as informações necessárias para permitir o acompanhamento da demanda.

Regras:
- Não criar tarefas duplicadas quando a mesma solicitação já estiver registrada.
- Campos ausentes devem ser identificados e tratados sem interromper todo o workflow.
- A prioridade deve seguir uma classificação simples: baixa, média ou alta.
- O prazo deve ser validado antes de ser utilizado nos lembretes.
- Apenas tarefas pendentes devem gerar lembretes.
- Registrar erros e situações inesperadas para facilitar a identificação de problemas.
- Evitar o uso de código quando houver um nó nativo do N8N capaz de realizar a mesma função.
- A automação deve ser simples, organizada e fácil de manter.

Explique quais nós do N8N devem ser utilizados e a lógica de funcionamento do workflow.
