# DOCKER

## Struttura consigliata:


```
docker/
├── db/
│   ├── docker-compose.yml
│   └── .env
```

Crea i file .env (mettilo accanto al docker-compose.yml) e docker-compose.yml

```
.env 
docker-compose.yml
```

## Come lanciare

cd docker/db
docker compose --env-file .env up -d
Se usi Docker Compose v2 (moderno, integrato in Docker), il file .env viene caricato automaticamente, quindi puoi fare semplicemente:

```
docker compose up -d
```

## User config
Soluzioni:

✅ Opzione 1: Usa sudo con docker-compose

```
sudo docker-compose up
```

oppure

```
sudo docker compose up
```
(la versione nuova di Compose non ha più il -, ma entrambe potrebbero funzionare a seconda della versione installata)

✅ Opzione 2: Aggiungi il tuo utente al gruppo docker (consigliato)

```
sudo usermod -aG docker $USER
```

Poi logout/login oppure esegui:

```
newgrp docker
```
Dopo, prova:

```
docker ps
```
Se funziona senza sudo, sei a posto.