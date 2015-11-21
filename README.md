## bdd-client

##TD 1 : Etude API et Clients
#Etude API

1. l’API GitHub : https://developer.github.com/v3/ permet:
	* d'obtenir les repertoires, les statistiques ect d'un utilisateur donne
	* de creer les repertoires,les branches ect d'un utilisateur donne
2. l' API de Météo, par exemple : https://developer.yahoo.com/weather/ permet :
	* d'obtenir la meteo actuelle d'une localisation donnee, ainsi que les previsions ect 

#Lister des requêtes possibles

1. Liste des 5 demande pouvant etre faite par une application cliente:
	* Pour l'API github:
		* Liste de repertoire d'un utilisateur donne 
		* Le nombre de commit dans un repertoire donne 
		* plusieurs statistique sur un utilisateur ou sur un repertoire 
	* Pour l'API meteo:
		* La meteo actuelle d'une localisation donnee
		* les previsions
2. Mon choix ce porte sur l'API Meteo 
3. Lister des requêtes POST.(je ne controlle pas l'atmosphere...pour l'instant!)
4. Requet GET :
`https://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20weather.forecast%20where%20woeid%20in%20(select%20woeid%20from%20geo.places(1)%20where%20text%3D%22nice%2C%20FR%22)&format=json&env=store%3A%2F%2Fdatatables.org%2Falltableswithkeys`

#Tester les requêtes

1. Le test avec la requet cite precedement avec postman a donne:
```
{
  "query": {
    "count": 1,
    "created": "2015-11-21T14:13:09Z",
    "lang": "fr-FR",
    "results": {
      "channel": {
        "title": "Yahoo! Weather - Nice, FR",
        "link": "http://us.rd.yahoo.com/dailynews/rss/weather/Nice__FR/*http://weather.yahoo.com/forecast/FRXX0073_f.html",
        "description": "Yahoo! Weather for Nice, FR",
        "language": "en-us",
        "lastBuildDate": "Thu, 12 Nov 2015 7:58 am CET",
        "ttl": "60",
        "location": {
          "city": "Nice",
          "country": "France",
          "region": ""
        },
        "units": {
          "distance": "mi",
          "pressure": "in",
          "speed": "mph",
          "temperature": "F"
        },
        "wind": {
          "chill": "57",
          "direction": "350",
          "speed": "8"
        },
        "atmosphere": {
          "humidity": "67",
          "pressure": "30.3",
          "rising": "0",
          "visibility": "6.21"
        },
        "astronomy": {
          "sunrise": "7:20 am",
          "sunset": "5:09 pm"
        },
        "image": {
          "title": "Yahoo! Weather",
          "width": "142",
          "height": "18",
          "link": "http://weather.yahoo.com",
          "url": "http://l.yimg.com/a/i/brand/purplelogo//uh/us/news-wea.gif"
        },
        "item": {
          "title": "Conditions for Nice, FR at 7:58 am CET",
          "lat": "43.7",
          "long": "7.25",
          "link": "http://us.rd.yahoo.com/dailynews/rss/weather/Nice__FR/*http://weather.yahoo.com/forecast/FRXX0073_f.html",
          "pubDate": "Thu, 12 Nov 2015 7:58 am CET",
          "condition": {
            "code": "28",
            "date": "Thu, 12 Nov 2015 7:58 am CET",
            "temp": "57",
            "text": "Mostly Cloudy"
          },
          "description": "\n<img src=\"http://l.yimg.com/a/i/us/we/52/28.gif\"/><br />\n<b>Current Conditions:</b><br />\nMostly Cloudy, 57 F<BR />\n<BR /><b>Forecast:</b><BR />\nThu - Partly Cloudy. High: 64 Low: 54<br />\nFri - Partly Cloudy. High: 64 Low: 55<br />\nSat - Partly Cloudy. High: 64 Low: 52<br />\nSun - Partly Cloudy. High: 63 Low: 51<br />\nMon - Sunny. High: 63 Low: 51<br />\n<br />\n<a href=\"http://us.rd.yahoo.com/dailynews/rss/weather/Nice__FR/*http://weather.yahoo.com/forecast/FRXX0073_f.html\">Full Forecast at Yahoo! Weather</a><BR/><BR/>\n(provided by <a href=\"http://www.weather.com\" >The Weather Channel</a>)<br/>\n",
          "forecast": [
            {
              "code": "30",
              "date": "12 Nov 2015",
              "day": "Thu",
              "high": "64",
              "low": "54",
              "text": "Partly Cloudy"
            },
            {
              "code": "30",
              "date": "13 Nov 2015",
              "day": "Fri",
              "high": "64",
              "low": "55",
              "text": "Partly Cloudy"
            },
            {
              "code": "30",
              "date": "14 Nov 2015",
              "day": "Sat",
              "high": "64",
              "low": "52",
              "text": "Partly Cloudy"
            },
            {
              "code": "30",
              "date": "15 Nov 2015",
              "day": "Sun",
              "high": "63",
              "low": "51",
              "text": "Partly Cloudy"
            },
            {
              "code": "32",
              "date": "16 Nov 2015",
              "day": "Mon",
              "high": "63",
              "low": "51",
              "text": "Sunny"
            }
          ],
          "guid": {
            "isPermaLink": "false",
            "content": "FRXX0073_2015_11_16_7_00_CET"
          }
        }
      }
    }
  }
}
```

#Conception Application Cliente
1. Liste des fonctionnalités pour l'utilisateur :
	* consulter la meteo actuelle d'une localisation donnee 
	* consulter les previsions meteo 
2. Fonctionalites applicatives
	*Avec un app mobile l'utilisateur :
		* cherche a avoir la temperature actuelle  instantanement 
		* Veut avoir les prevision des heures ou jours a venir en un coup d'oeil
	*Avec un app web l'utilisateur :
		* va plus chercher les details 
		* consulte l'historique
3. Faire des ébauches d’interfaces possibles pour deux applications clientes, une Mobile et une Web.
	![prototypeappapimeteo](https://cloud.githubusercontent.com/assets/15783589/11319119/4606e85a-906c-11e5-8044-caa33b819a67.png)
	![prototypeappapimeteo1](https://cloud.githubusercontent.com/assets/15783589/11319125/65312d76-906c-11e5-8cf6-4ed9a0057405.png)
