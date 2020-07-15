# caddy

Docker build to run a caddy server
``` 
cd mycaddy/phase1
docker build -t mycaddy:1.0 -t mycaddy:latest .
docker container run -d -p 8000:2015 --name mycaddy mycaddy

```


