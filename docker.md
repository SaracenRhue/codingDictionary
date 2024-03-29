# docker

install docker

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
rm -fr get-docker.sh
sudo usermod -aG docker $USER
sudo apt install docker-compose -y
sudo systemctl enable docker
```

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

Automate the process by running

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/SaracenRhue/dockerBuilder/main/start.sh)"
```

### docker run

```bash
docker run -d \
--name=helloworld \
-p 3000:3000 \ #host:container
-v /docker/appdata/helloworld:/home/app \ #host:container
--restart unless-stopped \
saracenrhue/helloworld:latest
```

## nodejs webserver

start a nodejs webserver on port `3000`

run

```bash
npm init
npm install http fs
```

```javascript
const http = require('http');
const fs = require('fs');

const server = http.createServer((req, res) => {
  res.writeHead(200, {'content-type': 'text/html'});
  fs.createReadStream('./index.html').pipe(res);
});

server.listen(process.env.PORT || 3000);
console.log('Server running at http://localhost:3000/');
```
