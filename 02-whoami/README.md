# 02 whoami

Här har vi lagt till en container och definierat router och service med namn whoami.

Starta med docker compose up -d och gå in på http://whoami.localhost för att se traefik routa till containern.

Testa även att skala upp till 3st whoami containers med :

docker compose up -d --scale whoami=3

Refresha sedan er browser och se att Traefik har detekterat de nya containers.


