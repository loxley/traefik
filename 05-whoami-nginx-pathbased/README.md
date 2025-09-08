# 05 whoami nginx pathbased

I detta exempel har vi två container, whoami och nginx.

En som kommer visa nginx om man går till http://demo.localhost/ :

      - "traefik.http.routers.web.rule=Host(`demo.localhost`) && PathPrefix(`/`)"

Här används både en Host rule och PathPrefix '/'.

I whoami containern har vi samma Host rule men PathPrefix '/api' istället,
det innebär att om vi går till http://demo.localhost/api så borde vi komma till whoami sidan.

I whoami så definierar vi också en middleware som ska plocka bort /api när requesten når whoami containern.

Om ni går till http://demo.localhost/api och letar efter 'GET' så står där inte '/api' eller hur?

Detta är för att vi tog bort det från requesten innan vi skickar vidare den till whoami containern.


