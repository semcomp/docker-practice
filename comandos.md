# Comandos úteis

## Limpando cache
```
docker rm -v $(docker ps -a -q -f status=exited) && \
docker rmi $(docker images -f "dangling=true" -q) && \
docker run -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker:/var/lib/docker --rm martin/docker-cleanup-volumes
```

## Nginx

### Rodar Nginx em Foreground

Bash
```
nginx -g "daemon off;"
```
Dockerfile
```
CMD ["nginx", "-g", "daemon off;"]
```

### Diretórios da imagem `nginx`

Arquivos HTML padrão
```
/usr/share/ngnix/html/
```
Arquivos de configuração
```
/etc/nginx/conf.d/
```
