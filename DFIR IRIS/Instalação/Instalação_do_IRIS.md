**-INSTALAÇÃO DO DOCKER**



lINK: https://github.com/carlossilva9867/soc-opensource-ia/blob/main/PARTE%201%20-%20INSTALACAO/000-docker\_install.md

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



apt-get -y update \&\& apt-get -y upgrade \&\& apt-get -y autoremove



apt-get update

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-Baixando o Script de Instalação do Docker**



curl -fsSL https://get.docker.com | sh



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**- Verificando a Instalação**



docker run hello-world



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-Verificar Docker Compose**



docker compose



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-INSTALAÇÃO DFIR-IRIS (Primeiro, você precisa clonar o repositório do DFIR-IRIS para o diretório /opt:)**



cd /opt



git clone https://github.com/dfir-iris/iris-web.git



cd iris-web



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-Configurando a Versão**



git checkout v2.4.22



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-Configurando o Ambiente**





cp .env.model .env



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_





**-ALTERANDO AS SENHA DO ARQUIVO .ENV**





POSTGRES\_PASSWORD:

POSTGRES\_ADMIN\_PASSWORD:

IRIS\_SECRET\_KEY:

IRIS\_SECURITY\_PASSWORD\_SALT:

IRIS\_ADM\_PASSWORD:



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

 

 administrator

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_





**-Alterar a porta - OPCIONAL**



\# -- LISTENING PORT

INTERFACE\_HTTPS\_PORT=8443



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-Construindo e Inicializando os Contêineres**

**-Puxe os contêineres do Docker:**



docker compose build



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**-Inicie o IRIS:**



docker compose up -d





\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**COMANDOS**



docker logs -f iriswebapp\_app - VERIFICAR LOG DO IRISWEBAPP

docker logs -f iriswebapp\_db - VERIFICAR LOG DO IRIS DB

docker logs -f iriswebapp\_nginx - VERIFICAR LOG DO IRIS NGINX



docker compose up -d -  SUBIR O DOCKER

nano docker-compose.base.yml - ARQUIVO DE CONFIGURAÇÃO

docker ps -a - VERIFICAR OS SERVIÇOS DO DOCKER DO IRIS

ss -tuln - VERIFICAR AS PORTAS

nano .env - ARQUIVO DE CONFIGURAÇÃO ENV

netstat -ltpnd

docker ps



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



ALTERAR A SENHA DE ADM WEB PELA WEB MESMO

