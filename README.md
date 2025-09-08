# traefik

## /etc/hosts

Vissa exempel kräver att vi kan använda vår browser för att testa traefik med ett visst hostname.

För att lägga till hosts i /etc/hosts på Mac/Linux så kör följande:

sudo nano /etc/hosts för att editera filen.

Därefter är det bara att lägga till fler hostnames efter localhost:

127.0.0.1       localhost frontend.localhost api.localhost backend.localhost whoami.localhost

På Windows bör den redan slå up allt framför localhost med *.localhost så här behöver man inte editera någon hosts fil.
