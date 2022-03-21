# Microserviço e Ciência de dados
**Bom dia, boa tarde ou boa noite!!😊**

Neste repositório estarei postando diariamente, durante 100 dias, minha jornada de aprendizado nas áreas de Backend e Ciência de dados. Busco com esse projeto aprender a construir uma arquitetura de microserviço e a desenvolver uma aplicação, utilizando ciência de dados. 

Ferramentas que tenho o objetivo de aprender nessa jornada:
- Flask;
- Docker;
- React;
- PostgreSQL;

Essa lista acima irá aumentar de tamanho a medida que for estudado os assuntos e achando outras ferramentas importantes. Com o passar do tempo, quando tiver aprendido o suficiente para entender como utilizar a mesma no código, irei colocar um ✅ do lado do nome.

Será uma jornada desafiante, mas irei me esforçar para escrever aqui todos os dias! Os dias serão documentados aqui mesmo, irei colocar um pequeno resumo do que estudei. Além disso, todos os links que achar interessante também irei inserir aqui.

---
## Links
#### [1][FreeCodeCamp Python Microservices Web App](https://www.youtube.com/watch?v=0iB5IPoTDts&list=PLNDjjx_fFhB30BPFWNqsLebpw4iveqjCH)
#### [2][Docker Documentation - Orientation and setup](https://docs.docker.com/get-started/)
<!-- #### [3][How to use Django with MongoDB]() -->

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
- [Como integrar o Django x MongoDB](tomato).
  - Djongo;
  - 
**Obs:** Como meu projeto não deve receber grande quantidade de dados e deve receber mais consultas, optei por prosseguir com o projeto utilizando o PostgreSQL. Caso o projeto cresça e venha a ter outras partes, então irei continuar a estudar o MongoDB.\
Links que utilizei para chegar nesta conslusão: [SQL vs NoSQL](), [When to use MongoDB rather than MySQL]() e [Usando o MongoDB com Django - IBM]()
</details>