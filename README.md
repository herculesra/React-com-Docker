# Desenvolvimento
## Comandos referente ao Docker

<p>Gerar imagem da aplicação:</p>

<code>$docker build -t sample:dev .</code>

<p>Criar o container a partir da imagem, setando alguns volumes:</p>

<code>$docker run -itd --rm -p 3001:3000 -v ${PWD}:/app -v/appnode_modules sample:dev</code>

- -itd inicia o container no modo iterativo do terminal e em background, é necessario no react.
- --rm remove o container caso ele seja parado (docker stop <'container'>)
- -p são as portas -> host:container
- -v volumes criados, para o hot reloading
- sample:dev nome da imagem.

## Forma mais rápida de executar 

### Usando o docker-compose podemos rapidamente inciar nosso container

<p>Monta a imagem e cria o container a partir dela:</p>

<code>$docker-compose up -d --build</code>

- -d para executar em background
- --build para fazer o build da imagem.

# Produção
## Build do Docker Production 
<code>$docker build -f Dockerfile.prod -t sample:prod .</code>

<p>Criando container de produção</p>

<code>$docker run -it --rm -p 1337:80 sample:prod</code>

## Executando o compose de produção

<p>Basta executar so este comando para colocar a aplicação em produção :D</p>

<code>$docker-compose -f docker-compose.prod.yml up -d --build</code>

# Comandos extras:

<p>Útil para encontrar o ip e outras conf do container</p>

<code>$docker inspect '<'nome_container'>' </code> 

<h3>Este projeto foi baseado no artigo do<a href="https://mherman.org/blog/dockerizing-a-react-app/">Michael Herman</a></h3>