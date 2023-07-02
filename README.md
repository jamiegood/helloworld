# Getting Started with [Fastify-CLI](https://www.npmjs.com/package/fastify-cli)

This project was bootstrapped with Fastify-CLI.

## Available Scripts

In the project directory, you can run:

### `npm run dev`

To start the app in dev mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

### `npm start`

For production mode

### `npm run test`

Run the test cases.

## Learn More

see secrets here:

https://learn.microsoft.com/en-us/azure/container-apps/manage-secrets?tabs=azure-portal

To learn Fastify, check out the [Fastify documentation](https://www.fastify.io/docs/latest/).

az login

docker build -t fastify-docker .

az acr build --registry $ACR_NAME --image $API_NAME .

az containerapp create \
 --name $API_NAME \
  --resource-group $RESOURCE_GROUP \
  --environment $ENVIRONMENT \
  --image $ACR_NAME.azurecr.io/$API_NAME \
 --target-port 3000 \
 --ingress 'external' \
 --registry-server $ACR_NAME.azurecr.io \
 --query properties.configuration.ingress.fqdn

docker build -t helloworld .

az acr build --registry thefullstackcontainerregistry --image helloworld .

az containerapp create \
 --name helloworld \
 --resource-group thefullstack-production \
 --environment thefullstack-container-app-env-production \
 --image thefullstackcontainerregistry.azurecr.io/helloworld \
 --target-port 3000 \
 --ingress 'external' \
 --registry-server thefullstackcontainerregistry.azurecr.io \
 --query properties.configuration.ingress.fqdn

http://thefullstackcontainerregistry.azurecr.io/

TRY THIS

az login --tenant ee7a106d-f6a8-4abe-bffd-58c24e240a34

az acr build --registry tfscontainerregistrydev.azurecr.io --image helloworld .

az containerapp create \
 --name helloworld \
 --resource-group thefullstack-production \
--environment thefullstack-container-app-env-production \
 --image tfscontainerregistrydev.azurecr.io/helloworld:latest \
 --target-port 3000 \
 --ingress 'external' \
 --registry-server tfscontainerregistrydev.azurecr.io \
 --query properties.configuration.ingress.fqdn
--environment-variables 'jamie'='set for containerapp create command' 'MinLength'='8'

## https://helloworld.whitecoast-48b44e9c.germanywestcentral.azurecontainerapps.io/example
