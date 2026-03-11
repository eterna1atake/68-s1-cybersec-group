## Cybersec Group Project

This is a group project for a cybersecurity class.

### Members

- Kittitat Mukdasanit (6602041620025)
- Supakorn Charoentong (ุ6602041610054)
- Krittanai Srisomros (6602041620033)
- Worrachat Sriburin (6602041610011)

## Environment
```sh
cp env.example .env
```

## Set a Virtual Hosting in local
```sh
sudo nano /etc/hosts 
```
### Save = Ctrl + O
### Exit = Ctrl + X

## Generate HTTPS and SSL Certificate
```sh
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
-keyout nginx-selfsigned.key \
-out nginx-selfsigned.crt \
-subj "/C=TH/ST=Bangkok/L=Bangsue/O=KMUTNB/CN=cybersec.group"
```

## Running a services
### Database
```
docker compose -f db.yaml up #monotoring
docker compose -f db.yaml up -d #background daemon
```

### Postgres admin
```
docker compose -f admin.yaml up #monotoring
docker compose -f admin.yaml up -d #background daemon
```

### Strapi Application
```
docker compose -f app.yaml up #monotoring
docker compose -f app.yaml up -d #background daemon
```

### Running 3 services in one line (etg.Database, PG Admin, Strapi)
```
docker-compose up #monotoring
docker-compose up -d #background daemon
```