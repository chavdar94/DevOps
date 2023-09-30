# Deploy with docker compose container

1. Create group
   `az group create --name "{custom name}" --location {location}`
2. Create resource group
   `az acr create --resource-group {group name} --name {custom name} --sku Basic --location {location}`
3. Login with group `az acr login --name {custum name} `
4. Build locally docker image `docker build -t {image name} {file directory}`
5. If the image is built push it azure group repository with `docker compose push`
6. Create docker context to connect docker with azure `docker context create aci {context name}`
7. Use the new context `docker context use {context name}`
8. Run the docker-compose.yaml file in the context `docker compose up -d`

- Might need to create a `Storage account` in Azure or define it in the `docker-compose.yaml` file.
