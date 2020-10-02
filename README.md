# frontend-challenge

## Iniciando o incrível desafio
Para a iniciar o desafio faça um `fork` desse repositório para o seu perfil pessoal, mas atente-se a ler todo o **README.md** antes porque o tempo para a solução do desafio começa a correr quando o `fork` é feito.

### :warning: Proposta do desafio
Então, a descrição do teste gerou alguns ruídos de comunicação nas issues [#2](https://github.com/quartacasa/frontend-challenge/issues/2) e [#1](https://github.com/quartacasa/frontend-challenge/issues/1). Lamentamos esse ruido e por isso editamos esse paragrafo para tentar deixa de forma mais explicita a intenção deste desafio.

A intenção deste desafio não é esperando que você seja um desenvolvedor especialista e que consiga desempenhar um resultado extremo em apenas 1 hora de trabalho, esse desafio aborda diversos cenários do segmento de front-end e para isso procuramos lança um desafio onde fizesse com que cada candidato pudesse se sentir vontade a atacar a área que fizesse mais sentido para ele como: UI/UX, Layout, React.js com Electron e etc. Por fim não espero o desafio entregue de forma completa mas sim com argumentos sobre solução dada ao escopo que foi entregue.

Sobre o prazo ser contato a partir do `fork` foi o meio que achamos de deixa todos os candidatos a vontade para começár quando bem entender, não queremos pressionar o processo de desenvolvimento, isso pode levar nós, enquanto empresa, perde pessoas boas como você.

Fique a vontade, e espero alem de se sentir desafio se divirta também.

## Descrição
Uma empresa te contratou para desenvolver um produto que gerencia projetos, onde equipes tem seus objetivos e cada objetivo tem suas tarefas. Todas as aplicações client-side criadas deverão funcionar de forma offline-first onde os membros das equipes possam marca suas tarefas como concluidas sem precisar está conectado a internet e para isso a empresa exerga necessita de ter aplicativo mobile, desktop e web para facilitar a relação membro de equipe e software.

## Requisitos para os projetos

### Design
Criar toda a `User Interface` e `User Experience` para o produto de forma responsiva utilizando o conceito de design system para o reaproveitamento dos componentes de UI.

### Tecnologia
Conversa vai, conversa vem e o setor de tecnologia achou interessante o reaproveitamento de código que se consegue ter com a biblioteca [React.js](https://pt-br.reactjs.org) logo acharam ideal usar [React.js](https://pt-br.reactjs.org/) para Web, [React Native](https://reactnative.dev/) para Mobile e [Electron](https://www.electronjs.org) com [React.js](https://pt-br.reactjs.org) para Desktop nativo.

### Negócio
A empresa que te contratou ja possui uma API onde será fácil integrar, ela é basicamente composta por quatro entidades: **User**, **Milestone**, **Roadmap**, **Task**.

#### Sobre a entidade User
**User** basicamente será a entidade responsável pela regra e dados relacionado aos usuários do software onde o mesmo terá dois níveis de permissionamento, que são:

- **Manager**: O gerenciador, ele cria um **Milestone**. A partir dai ele pode criar quantos **Roadmap**, com diversas **Task**, achar necessário para a conclusão de um **Milestone**.
- **Executor**: O executor, ele é o único quem pode executar as **Task** que compoem um **Roadmap**.

> :warning: Esses perfis de permissão são atribuidos a um **User** podendo ter quanto forem necessário, por exemplo, poderiamos ter um **Manager Executor** onde o mesmo iria criar um **Millestone**, criar um **Roadmap** e executar as **Tasks** criadas para esse **Roadmap**.


#### Sobre a entidade Milestone
**Milestone**, funciona como um chamado para execução de algo maior onde apenas um **User** com permissão de **Creator** pode criar um **Milestone**. Para a **Milestone** ser executada deverá ter algum **User** com permissão de **Manager** para afiliar-se a ela e assim criar um planejamento e execução, onde chamamos de **Roadmap**.

#### Sobre a entidade Roadmap
Todo **Roadmap** deve está atrelado a um **Milestone**, necessáriamente, o objetivo dele é organizacional e para isso não importa quantos **Roadmap** precisem ser criados. Todo **Roadmap** necessáriamente precisa ser composto ao menos por uma **Task** onde apenas o **User** com permissão **Manager** pode criar.

#### Sobre a entidade Task
Toda **Task** existe para ser executada por algum **Executor**, dado que a mesma foi executada o *status* dela muda para `done`.

### Sobre a API que deverá ser consumida

Endereço: http://challenge.quartacasa.com.br

#### Recursos

- Para consumir todos os dados de uma **Milestone**: `GET - /api/milestones`
- Para criar **Milestone**: `POST - /api/milestones`
```json
{
  "name": "string",
  "duration": "integer",
  "roadmaps": [
    {
      "name": "string",
      "duration": "integer",
      "tasks": [
        {
          "name": "string",
          "description": "string"
        }
      ]
    }
  ]
}
```
- Para atualizar um **Milestone**: `PUT - /api/milestones/:id`
- Para autorizar um usuário: `GET - /api/users/authorize/me`
- Para criar um usuário: `POST - /api/users`
```json
{
  "name": "string",
  "username": "string",
  "password": "string"
}
```

:triangular_flag_on_post: Todos os recursos da API necessitam de autenticação no formato [Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication), com excessão do recurso para criar o usuário.

Não se atente aos problemas que podem surgir na semântica com a API, a ideia é gerar um cenário de desconforto justamente para entender sua linha de raciocínio.

## Terminei, como entrego a solução?
Então, assumimos que tudo foi feito via `fork` desse projeto para o seu perfil pessoal como descrito [aqui](#iniciando-o-desafio). Depois de ter feito toda a solução basta abrir um `pull request` para a master e pronto, desafio entregue.

## Contatos para qualquer tipo de dúvida sobre o desafio
Email: guilherme@quartacasa.com.br
