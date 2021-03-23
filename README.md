# configurar o .env

## template

DATABASE_CLIENT=postgres
DATABASE_NAME=strapi
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_DB=strapi
DATABASE_USERNAME=strapi
DATABASE_PASSWORD=strapi

# configurar o docker-copose.yaml

## template -> docker-copose.yaml -> postgres

    version: "3"
    services:
      postgres:
        image: postgres
        container_name: ${DATABASE_NAME}
        ports:
          - ${DATABASE_PORT}
        env_file: .env
        environment:
          POSTGRES_DB: ${DATABASE_DB}
          POSTGRES_USER: ${DATABASE_USERNAME}
          POSTGRES_PASSWORD: ${DATABASE_PASSWORD}
        volumes:
          - ./data:/var/lib/postgresql/data

## MONGO

# depois instalar o docker(Pull the latest images)

    docker-compose pull

# depois ativar o docker(Run the stack) -> sempre usado para levantar o servidor

    docker-compose up -d
