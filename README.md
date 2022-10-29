# Challenge: Ad quality management service

[![Build Status](https://travis-ci.org/idealista/coding-test-ranking-dotnet.svg?branch=main)](https://travis-ci.org/idealista/coding-test-ranking-dotnet)

This repository contains a partially developed API to develop a service that is responsible for measuring the quality of ads. Your goal will be to implement the user stories described below.

The assumptions are based on a hypothetical *ads quality management team*, which requires a series of automatic checks to classify the ads based on a series of specific characteristics.

## Historias de usuario

* As head of the ad quality management team, I want to assign a score to an ad so that idealista users can sort ads from most complete to least complete. The ad score is a value between 0 and 100 that is calculated taking into account the following rules:
  * If the ad does not have any photos, 10 points will be deducted. Each photo in the listing earns 20 points if it's a high-resolution (HD) photo, or 10 if it's not.
  * That the ad has a descriptive text adds 5 points.
  * The size of the description also earns points when the ad is about a flat or a chalet. In the case of flats, the description earns 10 points if it has between 20 and 49 words or 30 points if it has 50 or more words. In the case of chalets, if it has more than 50 words, add 20 points.
  * That the following words appear in the description add 5 points each: Bright, New, Central, Renovated, Penthouse.
  * That the announcement is complete also contributes points. To consider a complete advertisement, it must have a description, at least one photo and the particular data of each type, that is, in the case of flats it must also have the size of the house, in the case of chalets, the size of the house and of garden. In addition, exceptionally, in garages it is not necessary for the advertisement to have a description. If the ad has all of the above data, provide another 40 points.

* As a quality manager, I want users not to see irrelevant ads so that the user always sees quality content on idealista. An ad is considered irrelevant if it scores less than 40 points.

* As a quality manager I want to be able to see the irrelevant ads and from what date they are irrelevant to measure the average quality of the content of the portal.

* As an idealista user, I want to be able to see the ads ordered from best to worst to easily find my home.

## Consideraciones importantes

En este proyecto te proporcionamos un pequeño *esqueleto* escrito en .Net Core 2.2 (puedes pasarlo a Framework 4.X o a otra versión de .Net core) 

En dicho *esqueleto* hemos dejado para que completes un [Controller] y un [Repository] en memoria. Puedes crear las clases y métodos que consideres necesarios.

**La persistencia de datos no forma parte del objetivo del reto**. Si no vas a usar el esqueleto que te proporcionamos, te sugerimos que la simplifiques tanto como puedas (con una base de datos embebida, "persistiendo" los objetos en memoria, usando un fichero...). **El diseño de una interfaz gráfica tampoco** forma parte del alcance del reto, por tanto no es necesario que la implementes.

**Nota:** No estás obligado a usar el proyecto proporcionado. Si lo prefieres, puedes usar cualquier otro lenguaje, framework y/o librería. Incluso puedes prescindir de estos últimos si consideras que no son necesarios. A lo que más importancia damos es a tener un código limpio y de calidad.

## Criterios de aceptación

* El código debe compilar y ser ejecutable :dancer:

* Debes proporcionar 3 endpoints: Uno para calcular la puntuación de todos los anuncios, otro para listar los anuncios para un usuario de idealista y otro para listar los anuncios para el responsable de del departamento de gestión de calidad.
