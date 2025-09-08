# 03 whoami multiple

Här definierar vi 3st whoami containers som alla tillhör samma router (whoami).

Testa att gå in på http://whoami.localhost och refresha och se när requests kommer till olika containers.

Vi har också satt --accesslog=true så då kan ni göra docker compose logs -f traefik och även se när den routar till olika backends.

Då borde ni se något liknande som här under:

docker compose logs -f traefik
traefik-1  | 192.168.65.1 - - [08/Sep/2025:17:36:51 +0000] "GET / HTTP/1.1" 200 692 "-" "-" 1 "whoami@docker" "http://172.18.0.4:80" 7ms
traefik-1  | 192.168.65.1 - - [08/Sep/2025:17:36:52 +0000] "GET / HTTP/1.1" 200 692 "-" "-" 2 "whoami@docker" "http://172.18.0.2:80" 2ms
traefik-1  | 192.168.65.1 - - [08/Sep/2025:17:36:52 +0000] "GET / HTTP/1.1" 200 692 "-" "-" 3 "whoami@docker" "http://172.18.0.3:80" 3ms
traefik-1  | 192.168.65.1 - - [08/Sep/2025:17:36:53 +0000] "GET / HTTP/1.1" 200 692 "-" "-" 4 "whoami@docker" "http://172.18.0.2:80" 2ms
traefik-1  | 192.168.65.1 - - [08/Sep/2025:17:36:53 +0000] "GET / HTTP/1.1" 200 692 "-" "-" 5 "whoami@docker" "http://172.18.0.3:80" 1ms

Testa även att sätta ett annat router namn istället för whoami och se vad som händer i dashboarden:

      - "traefik.http.routers.something.rule=Host(`whoami.localhost`)"
      - "traefik.http.routers.something.entrypoints=web"
      - "traefik.http.services.something.loadbalancer.server.port=80"

Prova även refresha och se vad som händer? Finns det fortfarande 3 backends?


