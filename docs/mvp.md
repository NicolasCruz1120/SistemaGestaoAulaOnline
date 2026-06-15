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

A funcionalidade inovadora proposta pelo grupo é a **Sala Virtual Interativa**:
um ambiente de aula ao vivo integrado à plataforma, sem necessidade de
ferramentas externas como Google Meet ou Zoom.

O diferencial não é a videochamada em si, mas as ferramentas pedagógicas
nativas em tempo real, que transformam a aula online em uma experiência
mais próxima da sala de aula presencial:

- **Enquetes ao vivo** — professor lança perguntas e o resultado aparece
  instantaneamente para todos
- **Fila de perguntas** — estudante levanta a mão digitalmente; professor
  gerencia quem fala
- **Reações em tempo real** — estudante sinaliza se entendeu ou está com
  dúvida sem interromper a aula
- **Quadro branco colaborativo** — professor e estudantes (quando liberado)
  escrevem e desenham juntos
- **Gravação da sessão** — aula fica disponível na turma para revisão posterior

### Problema que resolve
Professores que usam Meet ou Zoom perdem o vínculo entre a aula ao vivo e a
gestão da turma: presença é registrada manualmente, enquetes dependem de
ferramentas externas e não há histórico pedagógico das sessões.

### Benefícios esperados
- Aula ao vivo e gestão da turma no mesmo ambiente
- Maior engajamento dos estudantes durante a aula
- Registro automático de presença eliminando trabalho manual
- Histórico de sessões disponível para revisão

### Viabilidade técnica
Requer decisões arquiteturais específicas:
- **WebRTC** para comunicação de áudio/vídeo entre os participantes
- **WebSocket** para sincronização em tempo real das ferramentas interativas
- **Serviço de gravação** para armazenar e disponibilizar as sessões

### Impacto na arquitetura
A Sala Virtual Interativa justifica a adoção de uma arquitetura híbrida:
o núcleo da plataforma segue em camadas, enquanto o módulo de sala virtual
opera como um serviço independente via WebSocket e WebRTC, isolando a
complexidade de tempo real do restante do sistema.
