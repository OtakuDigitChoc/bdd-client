## bdd-client

##TD 1 : Etude API et Clients
#Etude API

1. l’API GitHub : https://developer.github.com/v3/ permet:
	- d'obtenir les repertoires, les statistiques ect d'un utilisateur donne
	- de creer les repertoires,les branches ect d'un utilisateur donne
2. l' API de Météo, par exemple : https://developer.yahoo.com/weather/ permet :
	- d'obtenir la meteo actuelle d'une localisation donnee, ainsi que les previsions ect 

#Lister des requêtes possibles

1. Liste des 5 demande pouvant etre faite par une application cliente:
	-Pour l'API github:
		- Liste de repertoire d'un utilisateur donne 
		- Le nombre de commit dans un repertoire donne 
		- plusieurs statistique sur un utilisateur ou sur un repertoire 
	-Pour l'API meteo:
		- La meteo actuelle d'une localisation donnee
		- les previsions
2. Mon choix ce porte sur l'API Meteo 
3. Lister des requêtes POST.(je ne controlle pas l'atmosphere...pour l'instant!)
4. Requet GET :
`https://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20weather.forecast%20where%20woeid%20in%20(select%20woeid%20from%20geo.places(1)%20where%20text%3D%22nice%2C%20FR%22)&format=json&env=store%3A%2F%2Fdatatables.org%2Falltableswithkeys`

#Tester les requêtes

1. Avec Postman, extension Chrome, tester les requêtes précédemment listées.

#Conception Application Cliente
1. Lister les fonctionnalités applications correspondant aux requêtes.
2. Hiérarchiser les fonctionnalités applicatives et les classer selon les deux types de clients : Mobile et Web.
3. Faire des ébauches d’interfaces possibles pour deux applications clientes, une Mobile et une Web.
