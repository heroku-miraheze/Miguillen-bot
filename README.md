Miguillen-bot
=============

Bot para realizar tareas en la Wikipedia en español y Wikidata

Para que el bot funcione hace falta bajarse la clase Snoopy la cual está disponible bajo licencia versión GNU General Public License 2.0 (GPLv2) en http://sourceforge.net/projects/snoopy/. 

El bot se compone de dos clases: BotWikidata y Botwiki. la primera cuenta con métodos que realizan funciones a partir del APi de Wikidata y la segunda del APi de Wikipedia en español. A partir de ambas clases se pueden desarrar diferentes módulos para efectuar tareas tanto en Wikidata como en la Wikipedia en español

Progresivamento iré introducciendo módulos para tal efecto por lo pronto he añadido:

* TransCoordWikidata. 
Este módulo se le tiene que dar una categoría que contenga una lista de artículos para trasladar sus coordenadas a Wikidata.
un for hace iteraciones con las páginas de la categoría. Primero comprueba que la página tiene elemento enlazado en Wikidata. Si la respuesta es negativa pregunta sobre si debe crearlo y espera confirmación. Al confirmar creará el elemento con el título de la página y el enlace a la wikipedia en español.
El paso siguiente es comprobar si el artículo tiene coordenadas en geoData de ser negativa la respuesta pasará a la siguiente iteración y si es positiva comprobará si el elemento de Wikidata tiene coordenadas (propieda p625) con valor. Si la respuesta es positiva pasará a la siguiente iteración y si es negativa preguntará si crea la decalración esperando respuesta de confirmación y al confirmar (s) creará la declaración con los valores que ha importado de geoData.
