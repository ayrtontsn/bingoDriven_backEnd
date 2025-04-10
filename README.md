#Link do bingo backend:
https://bingodriven-backend.onrender.com

#comando para fazer todos os testes do projeto COM DOCKER COMPOSE
    docker compose -f docker-compose-test.yml run backend npm run test:ci

#comando para subir o projeto SEM DOCKER COMPOSE
    docker build -t daily-kindness-backend .
    docker run -d --name back-end -p 5000:5000 daily-kindness-backend
    //disponibilizar para o frontend o endereço: (http://localhost:5000/)