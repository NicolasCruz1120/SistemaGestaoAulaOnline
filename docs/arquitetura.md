# Arquitetura de Software

## Estilo arquitetural escolhido

O sistema adota uma **arquitetura híbrida**, combinando:

- **Arquitetura em Camadas** para o núcleo da plataforma (autenticação,
  gestão de turmas, atividades e avaliações)
- **Serviço independente** para o módulo de Sala Virtual Interativa, que
  opera via WebSocket e WebRTC em razão da sua natureza de tempo real

## Justificativa

A arquitetura em camadas foi escolhida para o núcleo do sistema pelos
seguintes motivos:

- O domínio é bem definido e organizado em responsabilidades claras
  (apresentação, aplicação, domínio e infraestrutura)
- Facilita a manutenção e evolução dos módulos de forma independente
- É adequada ao porte e à complexidade do sistema proposto
- Reduz a complexidade operacional em comparação a uma arquitetura de
  microserviços completa

O módulo de Sala Virtual Interativa foi isolado como serviço independente
porque suas características técnicas — comunicação bidirecional em tempo
real, sincronização de estado entre múltiplos clientes e transmissão de
áudio/vídeo — são incompatíveis com o modelo requisição/resposta da
arquitetura em camadas.

## Camadas do sistema

┌─────────────────────────────────┐

│        Camada de Apresentação   │  Interface web (navegador)

├─────────────────────────────────┤

│        Camada de Aplicação      │  Controladores, casos de uso, APIs REST

├─────────────────────────────────┤

│        Camada de Domínio        │  Entidades, regras de negócio, serviços

├─────────────────────────────────┤

│      Camada de Infraestrutura   │  Banco de dados, e-mail, armazenamento

└─────────────────────────────────┘
┌──────────────────────┐
     │  Sala Virtual (WS)   │  Serviço independente via WebSocket/WebRTC
     └──────────────────────┘

## Decisões arquiteturais

### DA-01 — Adoção de arquitetura híbrida (camadas + serviço independente)

**Contexto:** o sistema possui dois perfis de operação distintos — o núcleo
transacional (turmas, atividades, avaliações) e o módulo de tempo real
(Sala Virtual Interativa).

**Decisão:** adotar arquitetura em camadas para o núcleo e isolar a Sala
Virtual como serviço independente.

**Justificativa:** misturar comunicação em tempo real com o modelo
requisição/resposta do núcleo aumentaria a complexidade sem benefício.
O isolamento permite evoluir cada parte de forma independente.

---

### DA-02 — Autenticação baseada em JWT

**Contexto:** o sistema possui múltiplos perfis de acesso (professor,
estudante, coordenador, administrador) com permissões distintas.

**Decisão:** utilizar autenticação stateless com tokens JWT (JSON Web Token).

**Justificativa:** tokens JWT eliminam a necessidade de sessões no servidor,
facilitam a integração entre o núcleo e o serviço de Sala Virtual, e são
amplamente suportados por bibliotecas e frameworks modernos.

---

### DA-03 — WebSocket para comunicação em tempo real na Sala Virtual

**Contexto:** a Sala Virtual Interativa exige sincronização imediata de
eventos entre múltiplos clientes (enquetes, reações, fila de perguntas).

**Decisão:** utilizar WebSocket para o canal de comunicação bidirecional
em tempo real.

**Justificativa:** o protocolo HTTP convencional não suporta comunicação
bidirecional contínua. WebSocket mantém a conexão aberta, permitindo que
o servidor envie eventos aos clientes sem requisição prévia, o que é
essencial para a experiência interativa da sala virtual.

---

### DA-04 — Armazenamento de arquivos em serviço externo

**Contexto:** estudantes e professores enviam arquivos (atividades, anexos,
gravações de aulas) que precisam ser armazenados com segurança e
disponibilidade.

**Decisão:** utilizar um serviço de armazenamento de objetos externo
(ex.: Amazon S3 ou similar) em vez de armazenar arquivos no servidor
da aplicação.

**Justificativa:** armazenar arquivos no servidor da aplicação cria
acoplamento entre escalabilidade de processamento e de armazenamento.
Serviços de objeto oferecem durabilidade, escalabilidade e URLs de acesso
sem onerar o servidor principal.

## Requisitos não funcionais considerados

| RNF | Descrição |
|---|---|
| Segurança | Controle de acesso por perfil com JWT; dados sensíveis não expostos |
| Disponibilidade | Sistema deve estar acessível durante horário letivo |
| Escalabilidade | Módulo de Sala Virtual isolado para escalar independentemente |
| Manutenibilidade | Separação em camadas facilita evolução e correção |
| Desempenho | WebSocket garante latência baixa nas interações em tempo real |
