# MVP — Minimum Viable Product

## Critério de priorização

As funcionalidades do MVP foram selecionadas com base em dois critérios:

1. **Valor essencial** — resolve o problema central da plataforma sem depender
   de recursos secundários
2. **Viabilidade técnica** — pode ser implementado de forma estável no prazo
   disponível

O objetivo do MVP é permitir que um professor gerencie uma turma completa —
da criação até a avaliação e que o estudante consiga acompanhar e entregar
suas atividades sem fricção.

## Funcionalidades do MVP

### Autenticação e controle de acesso
- Cadastro e login com e-mail e senha
- Perfis distintos: professor, estudante, administrador
- Recuperação de senha

### Gestão de turmas
- Criar, editar e arquivar turma
- Gerar link/código de convite
- Adicionar e remover estudantes

### Atividades
- Publicar atividade com título, descrição, prazo e anexos
- Definir tipo de entrega (arquivo ou texto)
- Entregar atividade dentro do prazo

### Avaliação
- Corrigir entrega com nota e comentário
- Publicar nota manualmente (visível ao estudante somente após publicação)
- Feedback estruturado por rubrica configurável

### Comunicação
- Mural de avisos da turma
- Comentários em avisos e atividades

### Acompanhamento
- Visão geral do estudante (turmas, pendências, notas)
- Painel do professor (entregas recebidas e atrasadas por atividade)

## Funcionalidades futuras

| Funcionalidade                        | Justificativa para adiar                                 |
|---------------------------------------|----------------------------------------------------------|
| Notificações automáticas por e-mail   | Requer serviço de agendamento e infraestrutura de e-mail |
| Login social (Google)                 | Depende de integração OAuth externa                      |
| Histórico de versões de entrega       | Complexidade de armazenamento adicional                  |
| Devolver atividade para reentrega     | Fluxo secundário, não bloqueia o uso principal           |
| Relatório de engajamento (coordenador)| Perfil de menor prioridade no MVP                        |
| Exportar notas em CSV                 | Conveniência, não essencial na primeira versão           |
| Calendário de prazos                  | Agrega valor mas não é bloqueador                        |
| Programar publicação de atividade     | Funcionalidade avançada para versões futuras             |
| Mensagem direta professor/estudante   | Mural de avisos cobre a comunicação essencial            |

## Funcionalidade inovadora

A funcionalidade inovadora proposta pelo grupo são as **notificações automáticas
por prazo**: o sistema envia um alerta por e-mail aos estudantes que ainda não
entregaram uma atividade quando o prazo está próximo (ex.: 24h antes).

Essa funcionalidade foi adiada do MVP por exigir uma decisão arquitetural
específica (serviço de agendamento + envio de e-mail), mas está prevista como
prioridade na primeira versão após o MVP.

