# SWAPI - The Star Wars API

The Star Wars API (SWAPI) is a programatically-formatted and accessible data set containing canonical information from the Star Wars film franchise. Structured in JSON format, the data presents quantified sets of information regarding the <strong>Films</strong> and a thorough statistical breakdown of the <strong>People, Species, Starships, Vehicles, and, Planets</strong> known in the Star Wars canon.

## How to use SWAPI

Accessing SWAPI can be completed through simple HTTP requests. On terminal, users can utilize the [curl](https://curl.haxx.se) command or install [httpie](https://httpie.org/) to test the requests. A simple request on terminal will be made to SWAPI's Base URL: https://swapi.co/api/, prefixed by either curl or http. For clarity, this documentation will make use of httpie. 

In order to make specific data requests, users must follow object notation formatting, attaching one of the six resources as a string and the corresponding id tag of the specific data:

For example, a user fetching data from the <strong>species</strong> resource will make the following request:```http https://swapi.co/api/species/```, whereas a user fetching data from <strong>planets</strong> will input:```http https://swapi.co/api/planets/```.

Generally, requests for data follows the format of: command URL/api/<strong>resource</strong>/

## Finding films with Luke Skywalker

To find films featuring Luke Skywalker, users can first make a request to SWAPI's <strong>People</strong> attribute with:

```http https://swapi.co/api/people/```

Making this request will yield a set of JSON objects with a number of <strong>People</strong> featured in the Star Wars films. SWAPI's <strong>People</strong> resource can be filtered via its <strong><em>name<em><strong> property, and using the following command:```http https://swapi.co/api/people/?search=luke```, will result in this:

```{
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
        {
            "birth_year": "19BBY",
            "created": "2014-12-09T13:50:51.644000Z",
            "edited": "2014-12-20T21:17:56.891000Z",
            "eye_color": "blue",
            "films": [
                "https://swapi.co/api/films/2/",
                "https://swapi.co/api/films/6/",
                "https://swapi.co/api/films/3/",
                "https://swapi.co/api/films/1/",
                "https://swapi.co/api/films/7/"
            ],
            "gender": "male",
            "hair_color": "blond",
            "height": "172",
            "homeworld": "https://swapi.co/api/planets/1/",
            "mass": "77",
            "name": "Luke Skywalker",
            "skin_color": "fair",
            "species": [
                "https://swapi.co/api/species/1/"
            ],
            "starships": [
                "https://swapi.co/api/starships/12/",
                "https://swapi.co/api/starships/22/"
            ],
            "url": "https://swapi.co/api/people/1/",
            "vehicles": [
                "https://swapi.co/api/vehicles/14/",
                "https://swapi.co/api/vehicles/30/"
            ]
        }
    ]
}```

The above object includes information on Luke Skywalker, including the film property, which lists the IDs for the films that Luke Skywalker appeared in.