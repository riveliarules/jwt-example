## Introdução

Este projeto se trata de um exemplo de implementação utilizando o framework FastAPI e JSON Web Tokens. O objetivo é analisar o impacto do uso do ASGI em relação ao WSGI.


## Como instalar/rodar este projeto

1. Na pasta do projeto - criar ambiente virtual
```
python3.9 -m venv fastapi-env
```
2. Ativar venv:
```
source fastapi-env/bin/activate
```
3. Instalar requirements.txt:
```
pip3 install -r requirements.txt
```
4. Rodar o servidor:
```
uvicorn blog.main:app --reload
```
5. E então acessar documentação do Swagger do FastAPI: http://127.0.0.1:8000/docs


## Entendendo o exemplo

Ao acessar a documentação, irá se deparar com a seguinte página:

![1](/uploads/de11213d1a6231909ab0b36c5444250d/1.png)

Não é possível utilizar as rotas /blog/ sem realizar autenticação. É possível autenticar-se clicando em "Authorize", que abrirá a seguinte tela:

![2](/uploads/907595a029e584fb9838a84d18305901/2.png)

A fins de exemplificação, podemos nos autenticar utilizando o usuário "user" e a senha "password".

![3](/uploads/f777dd2cb1753ef6c4d0e6d42ad03be8/3.png)

Após isso, passamos a ter acesso a todas as funcionalidades disponíveis em nossa documentação.

Essa autenticação é feita se utilizando de JWT. A implementação dessa funcionalidade foi feita conforme descrito na documentação do FastAPI: https://fastapi.tiangolo.com/tutorial/security/oauth2-jwt/


## Observações

Apesar de hoje ser possível criar aplicações em Python que se utilizam de ASGI utilizando Django ou Flask, a vantagem que o FastAPI possui em relação a estes frameworks é o suporte total ao uso das palavras reservadas _async_ e _await_. No entanto, nenhuma função deste projeto de exemplo foi declarada se utilizando da sintaxe `async def`. A documentação do FastAPI possui um capítulo sobre async / await, em que explica o que é código assíncrono como declarar as funções para trabalharem dessa forma. Ao explicar o uso do `async def` o autor diz que:
> Se você simplesmente não sabe, use apenas def.

que foi o caso dessa aplicação de exemplo. 
