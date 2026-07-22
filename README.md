# ⚡ API Serverless

<p>
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-7.0-3178C6?logo=typescript&logoColor=white">
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-24.x-339933?logo=nodedotjs&logoColor=white">
  <img alt="Serverless" src="https://img.shields.io/badge/Serverless-v4-FD5750?logo=serverless&logoColor=white">
  <img alt="AWS Lambda" src="https://img.shields.io/badge/AWS%20Lambda-FF9900?logo=awslambda&logoColor=white">
  <img alt="pnpm" src="https://img.shields.io/badge/pnpm-11.x-F69220?logo=pnpm&logoColor=white">
</p>

HTTP API em Node.js + TypeScript sobre AWS Lambda e API Gateway, feita com o Serverless Framework v4. Projeto de estudo.

## Stack

| Categoria       | Ferramenta                                            | Versão    |
| --------------- | ----------------------------------------------------- | --------- |
| Framework       | [Serverless Framework](https://www.serverless.com/)   | `v4`      |
| Runtime         | [Node.js](https://nodejs.org/)                        | `24.x`    |
| Linguagem       | [TypeScript](https://www.typescriptlang.org/)         | `^7.0.2`  |
| Package manager | [pnpm](https://pnpm.io/)                              | `^11.5.0` |
| Lint & Format   | [Biome](https://biomejs.dev/)                        | `2.5.4`   |

## Arquitetura

```mermaid
flowchart LR
    Client([Cliente]) -->|HTTP| APIGW[API Gateway<br/>HTTP API v2]

    subgraph AWS
        APIGW -->|GET /| Hello[λ hello]
        APIGW -->|GET /users/:userId| GetUser[λ getUserById]
    end
```

## Endpoints

| Método | Rota              | Resposta                          |
| ------ | ----------------- | --------------------------------- |
| GET    | `/`               | `{ "message": "Hello, World!" }`  |
| GET    | `/users/{userId}` | `{ "user": "<userId>" }`          |

## Rodando localmente

```bash
pnpm install
pnpm dev
```

```bash
curl http://localhost:3000/
curl http://localhost:3000/users/123
```

## Deploy

```bash
serverless deploy
```
