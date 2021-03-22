<p align="left">
  <img src="meu-pet-logo.svg" width="100" alt="Meu Pet Logo" /></a>
  <font size="7">Meu Pet</font>
</p>

## Descrição do projeto

API para a aplicação **Meu Pet 🐾**.

### Especificação técnica

Projeto desenvolvido com:
- [NestJS](https://github.com/nestjs/nest)

## Instalação das dependências

```bash
$ yarn install
```

## Execução da aplicação

```bash
# desenvolvimento
$ yarn run start

# modo watch
$ yarn run start:dev

# modo produção
$ yarn run start:prod
```

## Testes

```bash
# unit tests
$ yarn run test

# e2e tests
$ yarn run test:e2e

# test coverage
$ yarn run test:cov
```

## Estrutura de pastas do projeto

Baseada no projeto do github de [Clean Architecture](https://github.com/damienbeaufils/nestjs-clean-architecture-demo), que utiliza o conceito de arquitetura do [Uncle Bob - Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html).

```bash
|
|-- e2e   # Implementações dos testes de contrato dos controllers
|   |-- rest    # Classes de testes
|       |-- controller.e2e-spec.ts
|-- src
|   |-- domain   # Interfaces de repositories, especificações de erros, classes para objetos de domínio do repository
|       |-- invalid-user.error.ts
|       |-- __spec__    # Testes dos repositories de domínio, mockando as entidades
|           |-- user.spec.ts
|       |-- user.repository.ts
|       |-- user.ts   # Objeto de domínio
|   |-- infrastructure    # Contém configurações, implementações e não podem conter nenhuma regra de negócio
|       |-- app.module.ts
|       |-- config    # Configurações da aplicação
|           |-- environment-config.error.ts
|           |-- environment-config.module.ts
|           |-- environment-config.service.ts
|           |-- __spec__    # Testes unitários dos componentes de configuração
|               |-- environment-config.service.spec.ts
|           |-- typeorm-config.module.ts
|       |-- repositories    # Repositórios que implementam os domain repositories, expondo dados de domain apenas, fazendo integração com as entidades
|           |-- entities    # Entidades mapeadas com o banco de dados
|               |-- user.entity.ts
|           |-- repositories.module.ts
|           |-- user.repository.ts
|       |-- rest    # Controllers para requisições do front-end
|           |-- filters   # Filtros para validações das requisições
|               |-- auth0.filter.ts
|               |-- __spec__   # Testes dos Filtros para validações das requisições
|                   |-- auth0.filter.spec.ts
|           |-- models    # Classes de encapsulamento usadas pelo controller
|               |-- request
|                   |-- user-request.ts
|               |-- response
|                   |-- user-response.ts
|           |-- rest.module.ts
|           |-- user.controller.ts
|   |-- main.ts   # Arquivo de inicialização da aplicação
|   |-- use_cases   # Implementações de regras de negócio
|       |-- __spec__   # Testes das Implementações de regras de negócio
|           |-- user.service.spec.ts
|       |-- user.service.ts
|
|-- tsconfig.build.json
|-- tsconfig.json
```

<div>Icons made by 
  <a href="https://www.freepik.com" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a>
</div>