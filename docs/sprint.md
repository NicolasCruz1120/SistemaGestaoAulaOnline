# Diário de Sprint

## Informações gerais

| Campo               | Descrição                                          |
|---------------------|----------------------------------------------------|
| Projeto             |SmartClass — Plataforma de Gestão de Sala de Aula Online |
| Disciplina          | Modelagem e Projetos em Engenharia de Software     |
| Professora          | Fabricia Roos                                      |
| Ferramenta de gestão| GitHub Projects                                    |

## Divisão de responsabilidades

| Integrante | Responsabilidade principal                        |
|------------|---------------------------------------------------|
| Kauã Lima   | Visão do produto e stakeholders                   |
| Ives Henrique | Regras de negócio                                 |
| Eduardo Gonçalves | User stories                                      |
| Nicolas Cruz   | MVP, estrutura do repositório e quadro Kanban     |

---

## Aula 1 — Concepção da solução

### O que foi produzido
- Visão do produto (`visao-produto.md`)
- Identificação dos stakeholders (`stakeholders.md`)
- Regras de negócio (`regras-negocio.md`)
- User stories (`user-stories.md`)
- Definição do MVP (`mvp.md`)
- Estrutura do repositório GitHub
- Backlog e quadro Kanban no GitHub Projects
- `README.md`

### Principais decisões tomadas
- Definição do nome do sistema como SmartClass
- Escolha do GitHub Projects como ferramenta de gestão do backlog
- Definição da funcionalidade inovadora: Sala Virtual Interativa com
  ferramentas colaborativas em tempo real (enquetes, reações, fila de
  perguntas, quadro branco e registro automático de presença)
- Priorização do MVP com foco no fluxo completo professor → atividade →
  entrega → avaliação
- Adoção do critério valor ao usuário + viabilidade técnica para
  definição do escopo do MVP

### Dificuldades encontradas
- Alinhamento inicial sobre o escopo do MVP, especialmente em relação
  ao que incluir na primeira versão e o que adiar para versões futuras
- Definição de critérios de aceitação objetivos e verificáveis para
  as user stories
- Organização da divisão de tarefas entre os integrantes dentro do
  tempo disponível em aula

### Soluções adotadas
- Uso de critério duplo (valor essencial + viabilidade técnica) para
  priorização das funcionalidades do MVP
- Revisão coletiva das user stories para garantir critérios claros
  e testáveis em cada história
- Distribuição das responsabilidades por trilha de conteúdo em vez
  de por documento, garantindo coerência entre os artefatos

---

## Aula 2 — Projeto da solução

### O que foi produzido
- Diagrama BPMN do processo de entrega de atividade (`bpmn/`)
- Diagrama de casos de uso UML (`uml/`)
- Arquitetura de software (`arquitetura.md`)
- Modelo C4 Nível 1 — Contexto (`c4/contexto.png`)
- Modelo C4 Nível 2 — Containers (`c4/containers.png`)
- Decisões arquiteturais documentadas
- Apresentação final organizada (`apresentacao/`)

### Principais decisões tomadas
- Adoção de arquitetura híbrida: camadas para o núcleo da plataforma
  e serviço independente para a Sala Virtual Interativa
- Autenticação via JWT pela necessidade de suporte a múltiplos perfis
  de acesso com permissões distintas
- Uso de WebSocket para comunicação bidirecional em tempo real na
  Sala Virtual
- Armazenamento de arquivos em serviço externo (ex.: Amazon S3) para
  desacoplar armazenamento do servidor principal

### Dificuldades encontradas
- Definição do nível de detalhe adequado para os modelos C4, equilibrando
  clareza e completude
- Representação correta das raias e gateways no diagrama BPMN do
  processo de entrega de atividade
- Alinhamento entre os artefatos de modelagem e as decisões arquiteturais
  já documentadas

### Soluções adotadas
- Revisão conjunta dos modelos C4 com base nos exemplos do enunciado,
  focando nos elementos essenciais de cada nível
- Consulta à notação BPMN 2.0 para garantir o uso correto dos elementos
  no diagrama de entrega de atividade
- Validação cruzada entre arquitetura, regras de negócio e user stories
  para garantir coerência entre todos os artefatos produzidos
