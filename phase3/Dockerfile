ARG TAG=v2.1.1
FROM ubuntu AS buildstep
ARG TAG

RUN apt-get update && apt-get install -y gcc make git && ln -fs /usr/share/zoneinfo/America/Los_Angeles /etc/localtime
RUN apt-get install -y golang-1.14
COPY github-com.pem /etc/ssl/certs/
RUN git clone https://github.com/caddyserver/caddy.git
RUN mkdir /app && cp /caddy/cmd/caddy/main.go /app
RUN export PATH=$PATH:/usr/lib/go-1.14/bin; cd /app \
    && go mod init caddy \
    && go get github.com/caddyserver/caddy/v2@$TAG \
    && go build

FROM ubuntu
RUN mkdir -p /app
WORKDIR /app
COPY --from=buildstep /app/caddy /app/
COPY Caddyfile /app/
RUN groupadd -g 1001 caddy && useradd -r -u 1001 -g caddy -d /home/caddy -m caddy && chown -R caddy:caddy /app
USER caddy
EXPOSE 2015
CMD ["/app/caddy", "run"]




