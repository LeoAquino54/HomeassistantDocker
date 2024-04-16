# HomeassistantDocker
Instalação Homeassistantdocker

<h2>4.1 Docker CLI</h2>
<br>
<br>
sudo docker run -d \
  --name homeassistant \
  --privileged \
  --restart=unless-stopped \
  -e TZ=America/Sao_Paulo \
  -v /docker/home-assistant/config:/config \
  --network=host \
  ghcr.io/home-assistant/home-assistant:stable
  <br>
  <br>
  
<h2> 4.2 Docker Compose</h2>
<br>
<br>

sudo apt-get install docker-compose-plugin
<br>

<h3>Crie um arquivo chamado compose.yml com as seguinte informação:</h3>
<br>

version: '3'
<br>
services:
<br>
  homeassistant:
  <br>
    container_name: homeassistant
    <br>
    image: "ghcr.io/home-assistant/home-assistant:stable"
    <br>
    volumes:
    <br>
      - /docker/home-assistant/config:/config
      <br>
      - /etc/localtime:/etc/localtime:ro
      <br>
    restart: unless-stopped
    <br>
    privileged: true
    <br>
    network_mode: host
    <br>
    
<h2>Salve o arquivo e inicie.</h2>
<br>

sudo docker compose up -d
<br>
A grande vantagem de utilizar o método Docker Compose é que ele mantém armazenado todas as configurações utilizadas para criação do container, caso um dia você precisa utilizá-la novamente
<br>
<br>
<br>
<h1>Realizar acesso no localhost:8123</h1>
