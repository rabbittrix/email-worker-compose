# email-worker-compose
Comando do Docker

docker-compose exec db psql -U postgres -c '\l'
docker-compose down
docker-compose exec db psql -U postgres -f /scripts/check.sql
docker-compose exec db psql -U postgres -d email_sender -c 'select * from emails'
docker-compose logs -f -t
docker-compose up -d
docker-compose ps
docker-compose up -d --scale worker=3

docker-compose build or docker-compose up --build