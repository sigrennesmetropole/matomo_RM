# matomo_RM
Version Rennes Métropole de Matomo

## Docker 

Application Matomo installée au sein du serveur sig-testapp : /var/applications/matomo_RM

```bash
docker-compose up -d
```

URL : https://testapp.sig.rennesmetropole.fr/matomo/index.php

## Apache 

```bash
# Au niveau du <VirtualHost *:80>
<Location "/matomo/">
    ProxyPass "http://172.17.0.1:8090/"
    ProxyPassReverse "http://172.17.0.1:8090/"
</Location>

# Au niveau du <VirtualHost *:443>
<Location "/matomo/">
    ProxyPass "https://172.17.0.1:4435/"
    ProxyPassReverse "https://172.17.0.1:4435/"

    Header set Access-Control-Allow-Origin "*"
    Header set Access-Control-Allow-Methods "POST, GET, OPTIONS, DELETE, PUT"
    Header set Access-Control-Max-Age "1000"
    Header set Access-Control-Allow-Headers "x-requested-with, Content-Type, origin, authorization, accept, client-security-token"
</Location>
```