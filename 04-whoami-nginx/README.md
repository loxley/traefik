# 04 whoami nginx

I detta exempel definierar vi 2st olika containers som också har olika hostnames, whoami.localhost och nginx.localhost.

Detta visar att traefik kan hantera flera olika hostnames utan problem.

Testa även att ändra hostname på nginx routern till whoami.localhost och se vad som händer.

Routar traefik mellan både whoami och nginx efter ni gjort ändringen?

Efter ni har kontrollerat vad som händer så testa ta bort kommentaren med priority på whoami containern och se vad som händer.

Glöm inte göra docker compose up -d 
