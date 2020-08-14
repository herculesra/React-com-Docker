# Desenvolvimento
## Comandos referente ao Docker

Gerar imagem da aplicação:
$docker build -t sample:dev .

Criar o container a partir da imagem, setando alguns volumes:
$docker run -itd --rm -p 3001:3000 -v ${PWD}:/app -v/app/node_modules sample:dev

- -itd inicia o container no modo iterativo do terminal e em background, é necessario no react.
- --rm remove o container caso ele seja parado (docker stop <container>)
- -p são as portas -> host:container
- -v volumes criados, para o hot reloading
- sample:dev nome da imagem.

## Forma mais rápida de executar 

### Usando o docker-compose podemos rapidamente inciar nosso container

Monta a imagem e cria o container a partir dela:
$docker-compose up -d --build

- -d para executar em background
- --build para fazer o build da imagem.

# Produção
## Build do Docker Production 
$docker build -f Dockerfile.prod -t sample:prod .

Criando container de produção
$docker run -it --rm -p 1337:80 sample:prod

## Executando o compose de produção

Basta executar so este comando para colocar a aplicação em produção :D
$docker-compose -f docker-compose.prod.yml up -d --build

# Comandos extras:

$docker inspect <nome_container> //util para encontrar o ip e outras conf do container

<h3>Este projeto foi baseado no artigo do<a href="https://mherman.org/blog/dockerizing-a-react-app/">Michael Herman</a></h3>