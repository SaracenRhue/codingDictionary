# Docker

## Dockerfile

```dockerfile
FROM node:12

WORKDIR /home/app

ADD . .

RUN npm install

ENV PORT=3000

EXPOSE 3000

CMD [ "npm", "start" ]
```

### Bulding a multi-arch image

```bash
sudo systemctl start docker
docker login
docker buildx ls
docker buildx create --name mybuilder
docker buildx use mybuilder
docker buildx inspect --bootstrap
docker run -it --rm --privileged tonistiigi/binfmt --install all
docker buildx build --platform linux/amd64,linux/arm64 -t $USERNAME/$PROJECTNAME:latest . --push
```
