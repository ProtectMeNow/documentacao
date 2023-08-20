# Middleware

A arquitetura do código do **Middleware** é inspirada na **hexagonal architectrure**. Contendo as seguintes camadas:

- Application
- Domain
- Infrastructure
- UI

A camada de **domain** defini os objetos que serão manipulados no sistema, por exemplo o objeto de Usuário.

Na camada de **application**, é onde será realizada as manipulações de tudo que é definida na camada **domain**.

A camada de **infrastructure** é reponsável por impletar as interface declaradas pelo **domain**, onde será
utilizado as ferramentas oferecidas pelo framework ou pacotes externos.

Já na camada de **UI**, irá ser reponsável pela interação com os sistemas externos ou aplicativos, no caso API FULL REST.

![arquitetura-middleware](../_media/arquitetura-middleware.svg)
