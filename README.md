<center><h1>Microserviço e Ciência de dados</h1></center>

**Bom dia, boa tarde ou boa noite!!😊**

Neste repositório estarei postando diariamente, durante 100 dias, minha jornada de aprendizado nas áreas de Backend e Ciência de dados. Busco com esse projeto aprender a construir uma arquitetura de microserviço e a desenvolver uma aplicação, utilizando ciência de dados. 

Ferramentas que tenho o objetivo de aprender nessa jornada:
- Docker; 
- Django;✅ 
- Django REST framework;✅ 
- PostgreSQL;✅
- Celery;
- RabbitMQ;
- Flask;
- React;
- Elasticsearch;
  
Essa lista acima irá aumentar de tamanho a medida que for estudado os assuntos e achando outras ferramentas importantes. Com o passar do tempo, quando tiver aprendido o suficiente para entender como utilizar a mesma no código, irei colocar um ✅ do lado do nome.

Será uma jornada desafiante, mas irei me esforçar para escrever aqui todos os dias! Os dias serão documentados aqui mesmo, irei colocar um pequeno resumo do que estudei. Além disso, todos os links que achar interessante também irei inserir aqui.

---
## Links
#### [1][FreeCodeCamp Python Microservices Web App](https://www.youtube.com/watch?v=0iB5IPoTDts&list=PLNDjjx_fFhB30BPFWNqsLebpw4iveqjCH)
#### [2][Docker Documentation - Orientation and setup](https://docs.docker.com/get-started/)
#### [3][How To Use PostgreSQL with your Django](https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-django-application-on-ubuntu-14-04)
#### [4][Redis, Kafka or RabbitMQ: Which MicroServices Message Broker To Choose?](https://otonomo.io/redis-kafka-or-rabbitmq-which-microservices-message-broker-to-choose/)
#### [5][Deploy on Kubernetes](https://docs.docker.com/desktop/kubernetes/)

#### [6][How to Use Celery and RabbitMQ with Django](https://simpleisbetterthancomplex.com/tutorial/2017/08/20/how-to-use-celery-with-django.html)
---
<details>
<summary> Tarefas realizadas por dia</summary>

### Dia 1
- Estou seguindo o tutorial disponibilizado pelo freeCodeCamp [[1]](#links) para entender a estrutura de microserviço.\
Passos iniciais no terminal:
```shell
$ python3 -m venv ./venv 
$ source venv/bin/activate
$ pip install django
$ pip install djangorestframework
```
Hoje criei o ambiente virtual para instalar as dependências do projeto e, também, o projeto do django:
```shell
$ django-admin startproject admin .
$ python manage.py runserver
```
<!--  https://youtu.be/0iB5IPoTDts?list=PLNDjjx_fFhB30BPFWNqsLebpw4iveqjCH&t=439 -->

### Dia 2
- Adicionando Docker Files e lendo a documentação[[2]](#links)
- Preenchi o dockerfile.

### Dia 3
- Para preencher os requesimentos deste projeto (requirements.txt), comecei a ler mais sobre o mongodb;
- [Como integrar o Django x MongoDB]((https://www.mongodb.com/compatibility/mongodb-and-django)).
  - Djongo;

**Obs:** Como meu projeto não deve receber grande quantidade de dados e deve receber mais consultas, optei por prosseguir com o projeto utilizando o PostgreSQL. Caso o projeto cresça e venha a ter outras partes, então irei continuar a estudar o MongoDB.\
Links que utilizei para chegar nesta conslusão: [SQL vs NoSQL](https://youtu.be/t0GlGbtMTio), [When to use MongoDB rather than MySQL](https://medium.com/@rsk.saikrishna/when-to-use-mongodb-rather-than-mysql-d03ceff2e922) e [Usando o MongoDB com Django - IBM](https://developer.ibm.com/br/tutorials/os-django-mongo/)

### Dia 4
- Instalar PostgreSQL e inserir no arquivo de requirements.txt;
- Ler mais sobre a estrutura de microserviços;
> Modelando o projeto:
> - **Crawler:** irá puxar os produtos de uma página da web;
> - **Index:** passa os produtos para cá, utilizando elasticsearch.
> - **Webpage:** para procurar, pelos resultados retornados anteriormente, por meio de características dos itens, como nome, preço, etc.
> - Referências: [link](https://www.reddit.com/r/node/comments/hvyq38/any_project_ideas_to_learn_microservice/?utm_medium=android_app&utm_source=share)

Continuarei seguindo o vídeo do freecodecamp e depois irei tentar anexar essa ideia no meu projeto. 
<p>
Precisei istalar alguns pacotes realcionados com o postgresql, como <code>postgresql</code> e o <code>postgresql-contrib</code>, e configurar um banco de dados e usuário.<a href="https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-django-application-on-ubuntu-14-04">[3]</a>
</p>

<p>
Após realizar todo esse processo, precisei instalar o pacote <code>psycopg2</code>, que irá permitir o uso do banco de dados configurado anteriormente:
</p>

```shell
$ pip install django psycopg2
```

<p>
Em settings.py, mudei as configurações de <code>DATABASES</code> para conectar a um banco de dados PostgreSQL.
</p>

- Instalando django-cors-headers, para permitir solicitações no navegador para o seu aplicativo Django de outras origens.
  
```shell
$ pip install django-cors-headers
```

Inseri em apps instaldos: 

```ptyhon
INSTALLED_APPS = [
    ...,
    "corsheaders",
    ...,
]
```

Também precisei inserir na lista de classes de middleware, para permitir ler as responses.

```python
MIDDLEWARE = [
    ...,
    "corsheaders.middleware.CorsMiddleware",
    "django.middleware.common.CommonMiddleware",
    ...,
]
```
- Escolhendo um "Message Broker".[[4]](#links)
  - Message broker é um tipo de comunicação utilizado em microsserviços;
    - Comunicação assíncrona;
    - Permitindo que a comunicação seja estável e de confiança.
  - No projeto do vídeo do freecodecamp o instrutor optou pelo RabbitMQ.
    - Como não tenho o objetivo de receber grande quantidade de dados, irei utilizar o mesmo.
### Dia 5
Instalar o [celery + rabbitmq](https://simpleisbetterthancomplex.com/tutorial/2017/08/20/how-to-use-celery-with-django.html)
- Celery (Task Queue)

Hoje achei outra ferramenta interessante que é o **Kubernetes**. Irei ler um pouco sobre ele e achei vídeos interessantes: [Deploy Django into Production with Kubernetes, Docker, & Github Actions](https://www.youtube.com/watch?v=NAOsLaB6Lfc), [you need to learn Kubernetes RIGHT NOW!!](https://www.youtube.com/watch?v=7bA0gTroJjw).
- Kubernetes:
  - Orquestrador de containers;
  - Essa ferramenta permite criar várias instâncias de uma mesma imagem docker(container);
  - Útil quando a página possui muitos acessos e se faz necessário balancear os acessos entre as intâncias de um mesmo docker container;
  - Muitas ferramentas de cloud já possui a opção de se utilizar o Kubernetes;
  - Por enquanto, não irei utilizar essa ferramenta.

- Celery: 
  - Fila de tarefas assíncronas, que possui como base o envio de mensagens distribuídas;
  - Usada como estratégia para distribuir a carga de trabalho entre máquinas/threads.
  - O RabbitMQ envia e manda mensagens de forma externa pro celery.

Para instalar o celery e orabbitmq, foi utilizado este tutorial [[6]](#links).\
Instalando o Celery:
``` shell
$ pip install Celery
```

Intalando RabbitMQ:
```shell
$ sudo apt-get install -y erlang
$ sudo apt-get install rabbitmq-server
```

### Dia 6
- Configurar o docker [compose](admin/docker-compose.yml).
```shell
$ sudo snap install docker
$ docker-compose up #fazer o download dos requerimentos
```
<p>Apareceu um problema <code>PermissionError: [Errno 13] Permission denied</code>, isso ocorreu pois não tinha um soquete unix configurado. Para criar, achei essa alternativa no <a href="https://stackoverflow.com/questions/56784492/permissionerror-errno-13-permission-denied-manage-py">stackoverflow</a>.</p>

```shell
$ sudo chown $(whoami):$(whoami) /var/run/docker.sock
```

<p>Outro erro apareceu quando o comando <code>docker-compose up</code> foi utilizado: <code>python: can't open file '/app/manage.py': [Errno 2] No such file or directory</code>. Isso parece ocorrer pois 'volumes' do docker-compose não parece funcionar no ubuntu, pois não consegue montar o mesmo, de acordo com esse link no <a href="https://stackoverflow.com/questions/44694086/when-run-docker-compose-up-i-get-python-cant-open-file-manage-py-errno-2">stackoverflow</a>.<p>

### Dia 7
- Integração com banco de dados;
</details>