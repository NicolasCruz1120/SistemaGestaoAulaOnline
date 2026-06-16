### Regras de Negócio

#### RN01 – Apenas professores podem criar, editar, publicar ou remover atividades e avaliações das turmas sob sua responsabilidade.

**Descrição:** O gerenciamento das atividades acadêmicas é uma atribuição exclusiva dos professores vinculados à turma.

**Influências na solução:**

* **User Story:** Como professor, desejo criar e publicar atividades para disponibilizar tarefas aos estudantes.
* **Caso de Uso:** Criar Atividade e Gerenciar Avaliação.
* **BPMN:** As tarefas relacionadas à publicação de atividades pertencem exclusivamente à raia do Professor.
* **Arquitetura:** Necessidade de controle de acesso baseado em papéis (RBAC).
* **Requisito Não Funcional:** Segurança e integridade das informações acadêmicas.

---

#### RN02 – Somente alunos matriculados em uma turma podem acessar seus materiais, participar das aulas virtuais e realizar entregas.

**Descrição:** O acesso aos recursos acadêmicos depende da existência de matrícula ativa na turma correspondente.

**Influências na solução:**

* **Modelagem:** Criação da entidade associativa Matrícula entre Usuário e Turma.
* **Caso de Uso:** Acessar Turma e Enviar Atividade.
* **BPMN:** Validação automática do vínculo antes da execução da ação.
* **Arquitetura:** Implementação de verificações de autorização em todas as operações da turma.

---

#### RN03 – Toda atividade ou avaliação deve possuir prazo de entrega definido e o sistema deve impedir submissões após o vencimento.

**Descrição:** Nenhuma entrega poderá ser registrada após a data limite estabelecida pelo professor.

**Influências na solução:**

* **User Story:** Como professor, desejo definir prazos para organizar o cronograma acadêmico.
* **Caso de Uso:** Enviar Atividade.
* **BPMN:** Inclusão do gateway "Prazo expirado?" antes da submissão.
* **Modelagem:** Inclusão dos atributos dataPublicacao e dataLimite na entidade Atividade.
* **Arquitetura:** Validação automática de datas no servidor.
* **Requisito Não Funcional:** Confiabilidade do processo avaliativo.

---

#### RN04 – O registro de presença nas Salas Virtuais deve ocorrer automaticamente com base nos critérios definidos pela instituição.

**Descrição:** A presença será registrada a partir da participação efetiva do aluno na aula virtual, considerando critérios como tempo mínimo de permanência ou interação.

**Influências na solução:**

* **Diferencial do Produto:** Elimina registros manuais de frequência.
* **BPMN:** Inclusão do subprocesso automatizado "Registrar Presença".
* **Modelagem:** Criação da entidade Presença vinculada à Aula Virtual.
* **Arquitetura:** Integração entre os módulos Sala Virtual e Controle de Frequência.
* **Requisito Não Funcional:** Precisão e rastreabilidade dos registros.

---

#### RN05 – O sistema deve notificar automaticamente os usuários sobre eventos relevantes.

**Descrição:** Professores e alunos devem receber notificações relacionadas a novos comunicados, atividades publicadas, prazos próximos e alterações importantes.

**Influências na solução:**

* **User Story:** Como aluno, desejo receber lembretes para não perder prazos.
* **BPMN:** Inclusão da atividade automática "Enviar Notificação".
* **Arquitetura:** Necessidade de um serviço assíncrono de notificações.
* **Modelagem:** Entidade Notificação associada aos usuários.
* **Requisito Não Funcional:** Disponibilidade e desempenho.

---

#### RN06 – Coordenadores possuem acesso apenas para consulta e acompanhamento acadêmico.

**Descrição:** Coordenadores podem visualizar dados das turmas sob sua supervisão, mas não podem alterar notas, atividades ou informações pedagógicas.

**Influências na solução:**

* **Caso de Uso:** Consultar Relatórios Acadêmicos.
* **BPMN:** Fluxos de monitoramento executados na raia Coordenador.
* **Arquitetura:** Definição de permissões somente leitura.
* **Requisito Não Funcional:** Integridade e auditoria das informações.

---

#### RN07 – Administradores são responsáveis pela gestão global da plataforma e dos usuários.

**Descrição:** Apenas administradores podem cadastrar, bloquear, redefinir acessos ou remover usuários do sistema.

**Influências na solução:**

* **Caso de Uso:** Gerenciar Usuários.
* **BPMN:** Processo executado exclusivamente pelo Administrador.
* **Arquitetura:** Camada administrativa segregada das funcionalidades acadêmicas.
* **Requisito Não Funcional:** Segurança e governança do sistema.

---

### Influência das Regras na Solução Proposta

As regras de negócio não apenas restringem comportamentos, mas direcionam decisões de projeto.

A **RN03** impactou diretamente a modelagem e os processos de negócio. A necessidade de impedir entregas fora do prazo levou à criação de atributos específicos de controle temporal na entidade Atividade e à inclusão de um gateway decisório nos diagramas BPMN, garantindo a confiabilidade das avaliações.

Já a **RN04** influenciou significativamente a arquitetura do SmartClass. Como a proposta da plataforma inclui uma Sala Virtual Interativa integrada, tornou-se necessário desenvolver mecanismos automáticos de captura de participação, comunicação entre módulos e armazenamento estruturado dos registros de frequência. Essa decisão reforça o diferencial competitivo do produto ao reduzir tarefas administrativas dos docentes e aumentar a precisão dos dados acadêmicos.
