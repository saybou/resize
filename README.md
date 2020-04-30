# Resize

Resize and generate image from original file on AWS S3 with Node.js, according to parameters (sizes, path, etc.).

Project using Serverless and Typescript, ready to deploy on [AWS Lambda](https://aws.amazon.com/lambda) and [API Gateway](https://aws.amazon.com/api-gateway/).

Based on my [Serverless Typescript AWS example](https://github.com/saybou/serverless-typescript-aws).

## Stack

- [Node.js](https://nodejs.org/en/) 12x
- [Serverless](https://serverless.com/framework/docs/)
- [Typescript](https://www.typescriptlang.org/) (> 3.8) for type checking.
- A sample [docker-compose.yml](https://docs.docker.com/compose/), which allow us to test our App with [Docker](https://www.docker.com/).

## IDE Setup

[VSCode](https://code.visualstudio.com/) is highly preferred. Please ensure you have installed these extensions:

- Prettier
- Eslint

---

## Use with Docker

```bash
# host project dir
cd resize

# Up container
docker-compose up -d

# Attach to node container
docker exec -ti node sh

# container project dir
cd /var/www/resize

# install dependencies
npm install
```

## NPM scripts

```bash
# linter
npm run lint

# prettier
npm run prettier

# type checking
npm run typecheck
```
