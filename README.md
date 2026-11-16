# Desafio 01 — Task Manager API

> Primeiro desafio de desenvolvimento backend — .NET

## 1. Contexto

O objetivo deste desafio é desenvolver uma API REST para gerenciamento de tarefas (*Task Manager API*), utilizando ASP.NET Core.

A aplicação deverá permitir o gerenciamento básico de tarefas, utilizando armazenamento em memória, sem necessidade de configuração ou instalação de um banco de dados.

Este é o primeiro desafio de uma sequência de atividades que evoluirá progressivamente a aplicação, introduzindo novos requisitos técnicos, arquiteturais e operacionais.

Nesta primeira etapa, o foco está nos fundamentos de desenvolvimento de APIs, organização do código, qualidade de implementação e capacidade de tomar decisões técnicas.

**Importante:** você terá liberdade para definir a arquitetura e a organização interna da aplicação. As decisões tomadas serão consideradas durante a avaliação da entrega.

## 2. Objetivos

Ao concluir este desafio, espera-se que você consiga demonstrar conhecimentos sobre:

- Desenvolvimento de APIs REST utilizando ASP.NET Core.
- Organização e estruturação de projetos .NET.
- Separação de responsabilidades.
- Manipulação de dados em memória.
- Validação de dados e tratamento de erros.
- Utilização adequada dos métodos e códigos HTTP.
- Documentação de APIs.
- Testes automatizados.
- Utilização consciente de ferramentas de desenvolvimento assistido por IA.

## 3. Requisitos funcionais

A API deverá permitir o gerenciamento de tarefas.

### 3.1. Modelo de tarefa

Cada tarefa deverá possuir, no mínimo, os seguintes atributos:

| Atributo | Tipo | Descrição |
|---|---|---|
| Id | Guid | Identificador único |
| Title | string | Título da tarefa |
| Description | string | Descrição da tarefa |
| Status | Enum | Situação atual |
| CreatedAt | DateTime | Data de criação |
| UpdatedAt | DateTime? | Data da última atualização |
| DueDate | DateTime? | Data limite para conclusão |

Os status disponíveis deverão ser:

- Pending
- InProgress
- Completed

Você poderá adicionar outros atributos caso considere necessário, desde que justifique sua inclusão.

### 3.2. Operações disponíveis

A API deverá implementar as seguintes operações:

| Método | Endpoint | Descrição |
|---|---|---|
| POST | /api/tasks | Criar uma tarefa |
| GET | /api/tasks | Listar todas as tarefas |
| GET | /api/tasks/{id} | Consultar uma tarefa específica |
| PUT | /api/tasks/{id} | Atualizar uma tarefa |
| DELETE | /api/tasks/{id} | Excluir uma tarefa |

### 3.3. Regras de negócio

- Toda tarefa deverá possuir um identificador único.
- O título da tarefa é obrigatório.
- O título não poderá ser composto apenas por espaços em branco.
- A descrição poderá ser opcional.
- Uma tarefa deverá ser criada inicialmente com status Pending.
- A data de criação deverá ser definida automaticamente.
- A data de atualização deverá ser registrada quando uma tarefa for modificada.
- Não será permitido atualizar uma tarefa inexistente.
- Não será permitido excluir uma tarefa inexistente.
- Não será permitido atribuir um status que não esteja entre os valores definidos.

Considere também outros cenários de validação que julgar relevantes.

## 4. Requisitos técnicos

### 4.1. Plataforma

- .NET 8 ou superior.
- ASP.NET Core Web API.
- C#.
- Armazenamento de dados exclusivamente em memória.

### 4.2. Persistência

Nesta etapa, não deverá ser utilizado banco de dados externo.

Os dados deverão ser mantidos em memória durante a execução da aplicação.

Não utilize Entity Framework Core ou outros ORMs nesta etapa.

Considere que os dados serão perdidos quando a aplicação for encerrada ou reiniciada.

### 4.3. API

- Utilizar adequadamente os métodos HTTP.
- Retornar códigos HTTP apropriados para cada operação.
- Implementar validação das entradas.
- Tratar situações de erro.
- Disponibilizar documentação da API por meio de Swagger/OpenAPI.
- Permitir execução local da aplicação.

### 4.4. Testes

Implemente testes automatizados que contemplem, no mínimo:

- Criação de uma tarefa.
- Consulta de uma tarefa existente.
- Consulta de uma tarefa inexistente.
- Listagem de tarefas.
- Atualização de uma tarefa.
- Tentativa de atualização de uma tarefa inexistente.
- Exclusão de uma tarefa.
- Tentativa de exclusão de uma tarefa inexistente.
- Validação de dados obrigatórios.

Você poderá utilizar xUnit, NUnit ou MSTest.

## 5. Restrições

Para manter condições equivalentes entre os participantes, algumas restrições deverão ser respeitadas:

- Não utilizar bancos de dados.
- Não utilizar Entity Framework Core.
- Não utilizar serviços externos de armazenamento.
- Não implementar autenticação ou autorização.
- Não implementar mecanismos de cache distribuído.
- Não utilizar bibliotecas ou frameworks que implementem automaticamente as funcionalidades principais do desafio.

Bibliotecas auxiliares para documentação, testes e validação são permitidas.

A utilização de mecanismos nativos do ASP.NET Core é incentivada.

## 6. Utilização de inteligência artificial

O uso de ferramentas de desenvolvimento assistido por IA é permitido e incentivado.

Você poderá utilizar ferramentas como GitHub Copilot, OpenCode, Cursor ou outras disponíveis.

Entretanto, é fundamental compreender as soluções implementadas e conseguir explicar suas decisões técnicas.

Inclua no README do seu projeto uma seção chamada **Utilização de IA**, contendo:

1. Quais ferramentas foram utilizadas.
2. Como você utilizou essas ferramentas durante o desenvolvimento.
3. Quais atividades foram delegadas aos agentes.
4. Quais decisões técnicas foram tomadas por você.
5. Quais sugestões da IA foram modificadas ou rejeitadas e por quê.
6. Quais dificuldades foram encontradas durante o desenvolvimento.

Não existe penalização pelo uso de IA. O objetivo é avaliar sua capacidade de utilizar essas ferramentas como instrumentos de desenvolvimento, mantendo o domínio sobre o código produzido.

## 7. Entrega

A entrega deverá ser realizada por meio de um repositório público no GitHub.

### Passo a passo

1. Faça um fork deste repositório.
2. Desenvolva a solução no seu próprio repositório.
3. Mantenha o histórico de commits durante o desenvolvimento.
4. Documente a solução no README.
5. Certifique-se de que a aplicação pode ser executada seguindo as instruções documentadas.
6. Publique a versão final no seu GitHub.

### Estrutura mínima da documentação

Seu README deverá conter:

- Nome e descrição do projeto.
- Tecnologias utilizadas.
- Pré-requisitos.
- Instruções para execução.
- Como executar os testes.
- Decisões arquiteturais e técnicas.
- Utilização de IA.

Não é necessário seguir uma estrutura específica de diretórios ou projetos. A organização deverá refletir as decisões tomadas durante o desenvolvimento.

## 8. Critérios de avaliação

A avaliação será realizada considerando os seguintes aspectos:

| Critério | O que será observado |
|---|---|
| Arquitetura | Organização, separação de responsabilidades e acoplamento |
| Qualidade do código | Legibilidade, consistência e manutenibilidade |
| API REST | Contratos, métodos HTTP e códigos de resposta |
| Regras de negócio | Implementação correta dos requisitos |
| Validação e erros | Tratamento de entradas inválidas e situações inesperadas |
| Testes | Cobertura dos cenários e qualidade dos testes |
| Desempenho | Comportamento sob diferentes níveis de concorrência |
| Documentação | Clareza e facilidade de execução |
| Uso de IA | Capacidade de utilizar, revisar e compreender o código produzido |

### Avaliação de desempenho

A solução também será submetida a testes de carga.

Serão observados indicadores como:

- Throughput (requisições por segundo).
- Latência média.
- Percentis P95 e P99.
- Taxa de erros.
- Consumo de CPU e memória.
- Comportamento sob concorrência.

Os testes serão realizados em um ambiente controlado, com cenários definidos durante a avaliação.

Não existe uma meta mínima de requisições por segundo previamente estabelecida. O objetivo é compreender o comportamento da aplicação e identificar possíveis gargalos.

## 9. Apresentação da entrega

Após a conclusão, você deverá apresentar sua solução e estar preparado para:

- Explicar a arquitetura escolhida.
- Justificar as principais decisões técnicas.
- Demonstrar o funcionamento dos endpoints.
- Explicar como os dados são armazenados e manipulados.
- Apresentar os testes automatizados.
- Discutir possíveis limitações da implementação.
- Explicar como utilizou as ferramentas de IA.

Durante a apresentação, poderão ser propostos cenários adicionais e pequenas alterações nos requisitos.

## 10. Considerações finais

Este desafio não possui uma única solução correta.

Existem diferentes maneiras de organizar e implementar uma aplicação como esta. O importante é que as decisões tomadas sejam coerentes com o problema apresentado e que você consiga explicar os motivos por trás delas.

Não tente antecipar todos os requisitos que uma aplicação de produção poderia ter. Trabalhe com o escopo proposto, priorizando simplicidade, qualidade e clareza.

**O objetivo não é apenas fazer funcionar. É construir algo que você consiga compreender, explicar, testar e evoluir.**

Boa implementação!
