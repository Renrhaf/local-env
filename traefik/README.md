# Traefik

See https://github.com/Heziode/traefik-v2-https-ssl-localhost

```bash
# If it's the firt install of mkcert, run
./mkcert/mkcert -install
# Generate certificate for domain "docker.localhost", "domain.local" and their sub-domains
./mkcert/mkcert -cert-file certs/local-cert.pem -key-file certs/local-key.pem "docker.localhost" "*.docker.localhost" "saas-production.loc" "*.saas-production.loc"
```

Create networks that will be used by Traefik:

```bash
docker network create proxy
``` 

Now, start containers with : 

```bash
# Start Traefik
docker-compose -f docker-compose.yml up -d
# Start "whoami" example
docker-compose -f whoami.yml up
```

You can now go to your browser at [whoami.docker.localhost](https://whoami.docker.localhost)
You can access to Træfik dashboard at: [traefik.docker.localhost](https://traefik.docker.localhost)
