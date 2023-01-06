# matomo_RM
Version Rennes Métropole de Matomo

## Docker 

```bash
docker-compose up -d
docker exec -it matomo_rm-app-1 //bin//sh
cd config
vi config.ini.php # modifier trusted_hosts[]="localhost" en trusted_hosts[]="localhost:8080"
```

## Apache 

```bash
# Au niveau du <VirtualHost *:80>
<Location "/matomo/">
    ProxyPass "http://172.17.0.1:8090/"
    ProxyPassReverse "http://172.17.0.1:8090/"
</Location>

# Au niveau du <VirtualHost *:443>
<Location "/matomo/">
    ProxyPass "https://172.17.0.1:8090/"
    ProxyPassReverse "https://172.17.0.1:8090/"
</Location>
```