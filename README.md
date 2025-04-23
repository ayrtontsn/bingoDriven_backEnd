#Link do bingo backend:
https://bingodriven-backend.onrender.com

# Criar o arquivo `.env` com base no exemplo do `.env.example`;
# Criar o arquivo `.env.test` com:
    DATABASE_URL = "postgres://postgres:postgres@postgres:5432/postgres?schema=public"
    POSTGRES_PASSWORD: "postgres"
    POSTGRES_USER: "postgres"
    POSTGRES_DB: "tests"

#comando para fazer todos os testes do projeto COM DOCKER COMPOSE
    docker compose -f docker-compose-test.yml run backend npm run test:ci

#comando para subir o projeto SEM DOCKER COMPOSE
    docker build -t daily-kindness-backend .
    docker run -d --name mypostgres --network mynetwork -p 5432:5432 -e POSTGRES_PASSWORD=postgres postgres

    # devem estar na mesma `--network`, nesse caso chamo de `mynetwork`

    docker run -d --name back-end --network mynetwork -e DATABASE_URL=postgresql://postgres:postgres@mypostgres:5432/mydb?schema=public -p 5000:5000 daily-kindness-backend

    # disponibilizar para o frontend o endereço: (http://back-end:5000/)