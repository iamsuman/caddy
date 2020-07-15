# caddy

Docker build to run a caddy server on ubuntu image
``` 
phase 1
git clone git@github.com:iamsuman/mycaddy.git
cd mycaddy/phase1
docker build -t mycaddy:1.0 -t mycaddy:latest .
docker container run -d -p 8000:2015 --name mycaddy mycaddy
```
Verify: http://localhost:8000

```
phase 2: SSL
git clone git@github.com:iamsuman/mycaddy.git
cd mycaddy/phase1
docker build -t mycaddy:2.0 -t mycaddy:latest .
docker container run -d -p 8000:2015 --name mycaddy2 mycaddy

```
Verify: https://localhost:8000


