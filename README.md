# frontend-challenge

## Iniciando o desafio
Para a iniciar o desafio faça um `fork` desse repositório para o seu perfil pessoal, mas atente-se a ler todo o **README.md** antes porque o tempo para a solução do desafio começa a correr quando o `fork` é feito.

## Descrição
Uma empresa te contratou para desenvolver um projeto de gerenciamento de projeto, onde equipes tem seus objetivos e cada objetivo tem suas tarefas. Todas as aplicações client-side criadas deverão funcionar de forma offline-first onde os membros das equipes possam marca suas tarefas como concluidas sem precisar está conectado a internet. Contudo a empresa necessita de aplicativo mobile, desktop e web para facilitar a relação membro de equipe e software.

## Requisitos para os projetos

### Tecnologia
Conversa vai, conversa vem e o setor de tecnologia achou interessante o reaproveitamento de código que se consegue ter com a biblioteca React.js logo acharam ideal usar React.js para Web, React Native para Mobile e Electron com React.js para Desktop nativo.

### Negócio
A empresa que te contratou ja possui uma API onde será fácil integrar, ela é basicamente composta por quatro entidades: **User**, **Milestone**, **Roadmap**, **Task**.

#### Sobre a entidade User
**User** basicamente será a entidade responsável pela regra e dados relationado aos usuários do software onde o mesmo terá três níveis de permissionamento, que são:

- **Creator**: O criador, ele simplesmente cria um **Milestone**, porem ele mesmo não será o executador do seu **Milestone**.
- **Manager**: O gerenciador, ele se afilia a algum **Milestone** já criado por outro usuário. A partir dai ele pode criar quantos **Roadmap**, com diversas **Task**, achar necessário para a conclusão de um **Milestone**.
- **Executor**: O executor, ele é o único quem pode executar as **Task** que compoem um **Roadmap**.

> :warning: Esses perfis de permissão são atribuidos a um **User** podendo ter quanto forem necessário, por exemplo, poderiamos ter um **Manager Executor** onde o mesmo iria se afiliar a um **Millestone**, criar um **Roadmap** e executar as **Tasks** criadas para esse **Roadmap**.


#### Sobre a entidade Milestone
**Milestone**, funciona como um chamado para execução de algo maior e ela e só um **User** com permissão de **Creator** pode criar uma **Milestone**. Para a **Milestone** ser executada deverá ter algum **User** com permissão de **Manager** para afiliar-se a ela e assim criar um planejamento e execução, onde chamamos de **Roadmap**.

#### Sobre a entidade Roadmap
Todo **Roadmap** ele deve está atrelado a uma **Milestone**, necessáriamente, o objetivo dele é organizacional e para isso não importa quaantos **Roadmap** precisem ser criados. Todo **Roadmap** necessáriamente precisa ser composto ao menos por uma **Task** onde apenas o **User** com permissão **Manager** pode criar.

#### Sobre a entidade Task
Toda **Task** existe para ser executada por algum **Executor**, dado que a mesma foi executada o *status* dela muda para `done`.

### Sobre a API que deverá ser consumida
> TODO: Desenvolver a API que será consumida pelo desafio com documentação em Swagger

## Pontos que serão avaliados

- [ ] O quanto foi coerente com a descrição do problema e os requisitos do projeto
- [ ] O desaclopamento das lógicas de negócios para melhor manutenção do código
- [ ] O reproveitamento de código
- [ ] A organização de pastas
- [ ] Testes
- [ ] Facilidade para iniciar a aplicação
- [ ] Documentação
- [ ] Reaproveitamento de componentes entre aplicativos *(Mobile, Desktop, Web)*

## O que contará como ponto extra

- [ ] Será legal se tiver algum Dockerfile ou docker-compose
- [ ] Tudo escrito usando TypeScript

## Terminei, como entrego a solução?
Então, assumimos que tudo foi feito via `fork` desse projeto para o seu perfil pessoal como descrito [aqui](#iniciando-o-desafio). Depois de ter feito toda a solução basta abrir um `pull request` para a master e pronto, desafio entregue.

## Contatos para qualquer tipo de dúvida sobre o desafio
Email: guilherme@quartacasa.com.br
