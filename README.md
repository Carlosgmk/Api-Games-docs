# Api de Games
Esta Api é utilizada

## Endpoints
### GET /games 
Esse endopoint é responsavel por retornar a listagem de todosos games cadastrados no banco de dados.
#### Parametros
Nenhum

#### Respostas
##### Ok ! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo: 
```
[
    {
       id: 21,
       title: 'Good of War',
       price: 10.99,
       description: 'this is game 1',
       year: 2020        
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça significa que aconteceu alguma falha durante o processo de autenticação da requisição, Motivos: Token inválido, Token expired.

Exemplo:
```
{
    "message": "Invalid token"
}
```

### Post /auth 
Esse endopoint é responsavel por fazer o processo de Login.
#### Parametros
 email: 'E-mail do usuario cadastrado no sistema'
 
 password: 'Senha do usuario cadastrado no sistema'

 ##### Exemplo:
 ```
  {
   "email": "teste123@gmail.com",
   "password": "carlo1223"
  }
 ```

#### Respostas
##### Falha na autenticação! 400
Caso essa resposta aconteça possivelmente é algum erro interno ao gerar o token.

Exemplo: 
```
{err:'Falha interna'}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça significa que a senha esta errada.

Exemplo:
```
{err: 'senha errada!'}
```

##### ok! 200
Caso essa resposta aconteça significa que o login foi um sucesso e você recebe o token JWT para acessar os Endpoints.

Exemplo:
```
{token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ0ZXN0ZTEyM0BnbWFpbC5jb20iLCJpYXQiOjE3Mzg4MDAyNTksImV4cCI6MTczODk3MzA1OX0}
```

##### 404
Caso essa resposta aconteça significa que o email esta errado ou não existe no Banco de dados.

Exemplo:
```
{err: 'Email Invalido, não existe no BD !'}
```

##### 400
Caso essa resposta aconteça significa que o email esta errado ou a senha.

Exemplo:
```
{err: 'Email Invalido ou senha !'}
```



