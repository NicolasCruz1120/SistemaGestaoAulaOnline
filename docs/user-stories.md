## User Stories

### US01 – Criar Atividade

**Como** professor,
**quero** criar atividades para minha turma,
**para que** os alunos possam acessar e realizar as tarefas propostas.

**Critérios de Aceitação:**

* O professor deve estar autenticado no sistema.
* O professor deve selecionar uma turma sob sua responsabilidade.
* A atividade deve possuir título, descrição e prazo de entrega.
* A atividade deve ficar disponível para os alunos após sua publicação.
* Os alunos da turma devem receber uma notificação sobre a nova atividade.

---

### US02 – Entregar Atividade

**Como** aluno,
**quero** enviar minhas atividades pela plataforma,
**para que** o professor possa avaliá-las.

**Critérios de Aceitação:**

* O aluno deve estar matriculado na turma.
* O sistema deve permitir anexar arquivos ou enviar respostas textuais.
* A entrega deve ser registrada com data e horário.
* O sistema deve impedir entregas após o prazo definido.
* O aluno deve receber uma confirmação da submissão.

---

### US03 – Participar de Aula Virtual

**Como** aluno,
**quero** participar das aulas virtuais integradas ao sistema,
**para que** eu possa acompanhar o conteúdo sem utilizar ferramentas externas.

**Critérios de Aceitação:**

* O aluno deve estar matriculado na turma.
* O acesso à aula deve ocorrer diretamente pela plataforma.
* O aluno deve poder utilizar chat, enquetes e fila de perguntas.
* A presença deve ser registrada automaticamente.
* O sistema deve permitir acesso apenas durante o período da aula.

---

### US04 – Lançar Notas

**Como** professor,
**quero** registrar notas das atividades e avaliações,
**para que** os alunos acompanhem seu desempenho acadêmico.

**Critérios de Aceitação:**

* Apenas o professor responsável pela turma pode lançar notas.
* O sistema deve armazenar o histórico das avaliações.
* Os alunos devem visualizar apenas suas próprias notas.
* Alterações de notas devem ser registradas em log.
* O sistema deve atualizar automaticamente a média do aluno.

---

### US05 – Receber Notificações

**Como** aluno,
**quero** receber notificações sobre atividades, provas e avisos,
**para que** eu não perca prazos importantes.

**Critérios de Aceitação:**

* O sistema deve enviar notificações para novas atividades.
* O sistema deve avisar sobre prazos próximos do vencimento.
* O aluno deve visualizar notificações não lidas.
* As notificações devem permanecer acessíveis no histórico.
* O usuário deve poder marcar notificações como lidas.

---

### US06 – Publicar Comunicados

**Como** professor,
**quero** publicar comunicados para minha turma,
**para que** todos os alunos recebam informações importantes rapidamente.

**Critérios de Aceitação:**

* O comunicado deve ficar visível para todos os alunos da turma.
* O sistema deve registrar a data da publicação.
* Os alunos devem receber notificação automática.
* O professor pode editar ou remover comunicados publicados.
* O histórico de comunicados deve permanecer disponível.

---

### US07 – Consultar Relatórios Acadêmicos

**Como** coordenador,
**quero** visualizar relatórios de desempenho das turmas,
**para que** eu possa acompanhar os resultados acadêmicos.

**Critérios de Aceitação:**

* O coordenador deve acessar apenas turmas sob sua supervisão.
* O sistema deve apresentar médias, frequência e desempenho geral.
* O coordenador não pode alterar notas ou atividades.
* Os relatórios devem possuir filtros por turma e período.
* Os dados devem estar atualizados em tempo real.

---

### US08 – Gerenciar Usuários

**Como** administrador,
**quero** gerenciar os usuários da plataforma,
**para que** o acesso ao sistema seja controlado adequadamente.

**Critérios de Aceitação:**

* O administrador pode cadastrar novos usuários.
* O administrador pode bloquear ou reativar contas.
* O administrador pode redefinir senhas.
* Todas as operações devem ser registradas em auditoria.
* Usuários bloqueados não podem acessar o sistema.
