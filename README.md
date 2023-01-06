# matomo_RM
Version Rennes Métropole de Matomo

## Docker 

```bash
docker-compose up -d
docker exec -it matomo_rm-app-1 //bin//sh
cd config
vi config.ini.php # modifier trusted_hosts[]="localhost" en trusted_hosts[]="localhost:8080"
```