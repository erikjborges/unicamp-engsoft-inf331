# Apresentação do Lab02 - Data Flow & Mensagens

Estrutura de pastas:

~~~
├── README.md  <- arquivo apresentando a tarefa
│
└── notebook   <- arquivo do notebook
~~~

## Tarefa sobre catálogo de componentes

[Jupyter Notebook - Catálogo de componentes](notebook/components-01-catalog-erik.ipynb)

## Tarefa Web Components 1

~~~html
<dcc-trigger label="Mundo"
             action="noticia/mundo/politica"
             value="Noticia Mundo Politica">
</dcc-trigger>

<dcc-trigger label="Brasil P"
             action="noticia/brasil/politica"
             value="Noticia Brasil Politica">
</dcc-trigger>

<dcc-trigger label="Brasil E"
             action="noticia/brasil/esporte"
             value="Noticia Brasil Esporte">
</dcc-trigger>

<dcc-trigger label="Bahia"
             action="noticia/bahia/esporte"
             value="Noticia Bahia Esporte">
</dcc-trigger>

<dcc-lively-talk duration="0"
                 character="doctor"
                 speech="">
<subscribe-dcc topic="noticia/#/politica"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0"
                 character="nurse"
                 speech="">
<subscribe-dcc topic="noticia/brasil/#"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0"
                 character="patient"
                 speech="">
<subscribe-dcc topic="noticia/#"></subscribe-dcc>
</dcc-lively-talk>
~~~

## Tarefa Web Components 2

~~~html
<dcc-trigger label="Buscar Ciencia" action="ciencia/rss">
</dcc-trigger>

<dcc-rss publish="rss/ciencia" source="https://www.wired.com/category/science/feed">
  <subscribe-dcc topic="ciencia/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-trigger label="Buscar Design" action="design/rss">
</dcc-trigger>

<dcc-rss publish="rss/design" source="https://www.wired.com/category/design/feed">
  <subscribe-dcc topic="design/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-aggregator publish="ciencia/aggregate" quantity="3">
  <subscribe-dcc topic="rss/ciencia"></subscribe-dcc>
</dcc-aggregator>

<dcc-lively-talk duration="0"
                 character="doctor"
                 speech="">
<subscribe-dcc topic="ciencia/aggregate"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0"
                 character="nurse"
                 speech="">
<subscribe-dcc topic="rss/ciencia"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0"
                 character="patient"
                 speech="">
<subscribe-dcc topic="rss/design"></subscribe-dcc>
</dcc-lively-talk>
~~~
