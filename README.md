# caddy

Docker build to run a caddy server on ubuntu image
``` 
git clone git@github.com:iamsuman/mycaddy.git
cd mycaddy/phase1
docker build -t mycaddy:1.0 -t mycaddy:latest .
docker container run -d -p 8000:2015 --name mycaddy mycaddy

```


