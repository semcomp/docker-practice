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

## Registry

Rodar o container
```
docker run -d -p 5000:5000 --name registry registry:2
```

Tag
```
docker tag ubuntu localhost:5000/myfirstimage
```

Mapeando volumes
```
docker run -d -p 5000:5000 --restart=always --name registry \
  -v `pwd`/data:/var/lib/registry \
  registry:2
```
# Links Úteis

* Documentação Docker: https://docs.docker.com/engine/understanding-docker/
* Docker Hub: https://hub.docker.com/
* Mattermost: https://github.com/mattermost/mattermost-docker.git
