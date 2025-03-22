# conversao-distancia

Este readme descreve o projeto Docker para um aplicativo web que converte distâncias entre diferentes unidades. O projeto consiste em uma aplicação Flask que é executada dentro de um contêiner Docker. Abaixo estão os detalhes do projeto, incluindo os arquivos necessários, comandos Docker e instruções para execução.

## Arquivos do Projeto

**Dockerfile:** O Dockerfile define a imagem Docker para o projeto. Ele começa com uma imagem base do Python 3.10.12, configura o diretório de trabalho, instala as dependências listadas no requirements.txt, copia os arquivos do projeto para o contêiner e define o comando para iniciar o servidor Gunicorn.

**.gitignore:** O arquivo .gitignore especifica quais arquivos e diretórios devem ser ignorados pelo Git, como arquivos compilados do Python, diretórios de distribuição e arquivos de configuração.

**index.html:** O arquivo index.html é o template HTML usado pela aplicação Flask. Ele contém um formulário para selecionar a unidade de conversão e inserir o valor a ser convertido. O resultado da conversão é exibido na mesma página.

**app.py:** O arquivo app.py contém a lógica da aplicação Flask. Ele define uma rota para a página inicial, que exibe o formulário de conversão e processa as entradas do usuário para realizar a conversão de distância.

**requirements.txt:** O arquivo requirements.txt lista as dependências do projeto, incluindo Flask e Gunicorn.

## Comandos Docker

### Construir a Imagem Docker

Para construir a imagem Docker a partir do diretório do projeto, use o seguinte comando:
```
docker build -t conversao-distancia .
```

### Rodar a Imagem Docker Localmente

Para rodar a imagem Docker localmente e acessar a aplicação em http://localhost:5000, use o seguinte comando:
```
docker container run -d -p 5000:5000 conversao-distancia
```

### Enviar a Imagem para o Docker Hub

Para enviar a imagem Docker para o Docker Hub, primeiro tageie a imagem e depois use o comando docker push:
```
docker tag oliveirabsdocker/conversao-distancia-desafio:v1 oliveirabsdocker/conversao-distancia-desafio:latest
```
```
docker push oliveirabsdocker/conversao-distancia-desafio:latest
```

### Rodar a Imagem do Docker Hub

Para rodar a imagem diretamente do Docker Hub, use o seguinte comando:

```
docker container run -d -p 5000:5000 oliveirabsdocker/conversao-distancia-desafio:latest
```

## Conclusão

Este projeto Docker permite que você execute um aplicativo web de conversão de distância de forma fácil e consistente, independentemente do ambiente de desenvolvimento. Com os comandos Docker fornecidos, você pode construir, rodar e compartilhar a imagem Docker com facilidade.