# SWAPI - The Star Wars API

The Star Wars API (SWAPI) is a programatically-formatted and accessible data set containing canonical information from the Star Wars film franchise. Structured in JSON format, the data presents quantified sets of information regarding the <strong>Films</strong> and a thorough statistical breakdown of the <strong>People, Species, Starships, Vehicles, and, Planets</strong> known in the Star Wars canon.

## How to use SWAPI

Accessing SWAPI can be completed through simple HTTP requests. On terminal, users can utilize the 'curl' function or install 'httpie' to test the requests. A simple request on terminal will be made to SWAPI's Base URL: https://swapi.co/api/, prefixed by either curl or http. 

In order to make specific data requests, users must follow object notation formatting, attaching one of the six resources as a string and the corresponding id tag of the specific data:

- ```http https://swapi.co/api/people/```
- ```http https://swapi.co/api/films/```
- ```http https://swapi.co/api/species/```
- ```http https://swapi.co/api/starships/```
- ```http https://swapi.co/api/vehicles/```
- ```http https://swapi.co/api/planets/```

## Finding films with Luke Skywalker

To find films featuring Luke Skywalker, users can first make a request to SWAPI's <strong>People</strong> attribute with:

```http https://swapi.co/api/people/```

Making this request will yield a set of JSON objects with a number of <strong>People</strong> featured in the Star Wars films.
Each object will contain sub-attributes such as <em>name, birth_year, eye_color, and hair_color</em>. At its current state, SWAPI only allows search fields for one or two sub-attributes of each resource. For the <strong>People</strong> resource, the <em>name</em> sub-attribute can be searched through and used to isolate specific data sets using the following command:

```http https://swapi.co/api/people/?search=luke```

Inputting the above command will results in the specific data set for Luke Skywalker, including the sub-attribute <em>films</em>, which includes all the movies Luke Skywalker appeared in !