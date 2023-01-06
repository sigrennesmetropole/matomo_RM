# matomo_RM
Version Rennes Métropole de Matomo

## Docker 

```bash
docker-compose up -d
```

URL : http://testapp.sig.rennesmetropole.fr/matomo/

## Apache 

```bash
# Au niveau du <VirtualHost *:80>
<Location "/matomo/">
    ProxyPass "http://172.17.0.1:8090/"
    ProxyPassReverse "http://172.17.0.1:8090/"
</Location>
```