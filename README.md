# Using Traefik

## Quick-start

1. Start Traefik reverse proxy  
`docker-compose up -d reverse-proxy`

2. Start whoami web application  
`docker-compose up -d whoami`

3. Check the route which Traefik automatically create when new services deteted  
`curl -H Host:whoami.docker.localhost http://127.0.0.1`

4. Scale to 2 instance of whoami application  
`docker-compose up -d --scale whoami=2`

5. Check Traefik load-balances between the two instances of your service   
`curl -H Host:whoami.docker.localhost http://127.0.0.1`

- Dashboard  
`http://localhost:8080`

- Check Traefik API rawdata  
`http://localhost:8080/api/rawdata`

## Use Traefik with Official Docker Image

```docker run -d -p 8080:8080 -p 80:80 \
    -v $PWD/traefik.toml:/etc/traefik/traefik.toml traefik:v2.0```


