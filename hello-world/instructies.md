# Instructies Hello World

- Start een terminal 
- Download de NGINX webserver image: `docker pull nginx`
- Start een container, gebruikmakend van nginx image, en koppel poort 80 aan poort 80 van de container `docker run --rm -p 80:80 nginx`
- Ga met de browser naar localhost. De pagina verschijnt.
- Sluit de container af door in de terminal op `Ctrl + C ` te drukken

- Start en container en gebruik de website `docker run --rm -p 80:80 -v /home/harm/Projects/hello-world:/usr/share/nginx/html nginx`
- Ga met de browser naar localhost. De pagina verschijnt.
- Start gEdit op en open `index.html`
- Pas de tekst aan
- Ververs de browser. De tekst is veranderd.