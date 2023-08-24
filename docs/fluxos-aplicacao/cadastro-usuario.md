# Cadastro de usuário

### Introdução

O cadastro de usuário irá envolver os segintes componentes de nosso sistema distribuído:

- Firebase
- Aplicativo (android e ios)
- Middleware
- Backend

Onde o **Firebase**, será responsável por gerenciar o login e permitir a conexão com login social.

Já o **Aplicativo** será nosso front-end, ou seja, responsável por toda a interação com o usuário.

O **Middleware** irá fazer *"meio de campo"* entre o Backend, Aplicativo e Firebase.

O **Backend** terá a responsabilidade de persistir as informações de cadastro do usuário em nosso banco de dados.

### Registro de usuário

#### Sem login social

Para fazer o cadastro sem login social, o **Aplicativo** irá mandar e-mail, senha e confirmação da senha para
**Middleware**, onde o mesmo fará o registro do usuário no **Firebase**. Após a confirmação do registro, o **Middleware**
enviará a informações como e-mail e uid do usuário para o **Backend** como pré-cadastro, e retornará para **Aplicativo**
que já pode fazer o login e dar início ao cadastro usuário.

Com o término do cadastro no **Aplicativo**, as informações serão enviadas para o **Middleware**, que irá redireciona-las
para o **Backend**.

![login-nao-social](../_media/cadastro-usuario/login-nao-social.svg)

Ordem das ações do fluxo acima:

1. Registrar login (Aplicativo -> Middleware)
2. Criar usuário (Middleware -> Firebase)
3. Confirmação de usuário criado (Firebase -> Middleware)
4. Logar e prosseguir com o cadastro (Middleware -> Aplicativo)
5. Efetuar o login (Aplicativo -> Firebase)
6. Cadastro de usuário (Aplicativo -> Middleware)
7. Finalizar cadastro (Middleware -> Backend)

##### Endpoint, sem login social

Para o **Backend** será criado:

- Pré-cadastro
- Cadastro

Para o **Middleware** será criado:

- Registro login
- Cadastro

##### Telas do Aplicativo, sem login social

O Aplicativo terá as seguintes telas:

- Login
- Registrar Login
- Cadastro

#### Login social

Para este cadastro o **Aplicativo**, irá efetuar o login com o **Firebase**, com as informações retornadas irá para
tela de cadastro, preenchendo algumas informações previamente. Após o usuário completar seu cadastro, tudo será enviado
para o **Middleware** que redirecionará esses dados para o **Backend**, cuja a função será persistir os dados.

![login-social](../_media/cadastro-usuario/login-social.svg)

Ordem das ações do fluxo acima:

1. Efetuar o login (Aplicativo -> Firebase)
2. Informações do usuário (Firebase -> Aplicativo)
3. Cadastro de usuário (Aplicativo -> Middleware)
4. Finalizar cadastro (Middleware -> Backend)

##### Endpoint, login social

Para o **Backend** será criado:

- Cadastro

Para o **Middleware** será criado:

- Cadastro

##### Telas do Aplicativo, login social

O Aplicativo terá as seguintes telas:

- Login
- Cadastro
