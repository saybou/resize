# Resize

Resize and generate image from original file on AWS S3 with Node.js, according to parameters (sizes, path, etc.).

Project using Serverless and Typescript, ready to deploy on [AWS Lambda](https://aws.amazon.com/lambda) and [API Gateway](https://aws.amazon.com/api-gateway/).

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

## Configure AWS Credentials

### Create IAM user for Serverless

- Login to AWS and navigate to IAM
- Create a new user called serverless-admin
- Give serverless-admin Programatic access
- Attach the AdministratorAccess policy

Save your new AWS profile into `~/.aws/credentials` (Don't forget to set your values :D) :

```test
[serverless-admin]
aws_access_key_id = XXX
aws_secret_access_key = XXX
region = XXX
```

Set this profile in your `serverless.yml` so Serverless can use it for deployment.

```yaml
provider:
  profile: serverless-admin
```

(or pass it with `--profile` argument to `serverless deploy`command.)

## Deploy

```bash
# -v enables verbose output so you can see what happens
serverless deploy -v
```

Dev stage is assumed by default.

Invoke our function :

```bash
# -f specifies the function name, -l specifiesto output the logs to the console
serverless invoke -f hello -l
```

You can test it with your API Gateway end point : `https://xxxxxx.execute-api.us-east-1.amazonaws.com/dev`

## Delete your service

```bash
serverless remove
```
