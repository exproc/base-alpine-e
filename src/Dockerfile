FROM alpine:edge
LABEL Maintainer="Chris c <chris@cchalifo.xyz>"
LABEL Description="Alpine Linux edge, BasImage"
RUN mkdir -pv /etc/supervisor.d
RUN apk add -U tzdata bash supervisor nginx tftp-hpa
ENV TZ=America/New_York
RUN cp /usr/share/zoneinfo/America/New_York /etc/localtime 
RUN ls -la /etc/ 
RUN ln -sf /dev/stdout /var/log/nginx/access.log \ && ln -sf /dev/stderr /var/log/nginx/error.log
RUN mkdir -pv /var/www/html
COPY  src/etc/supervisor/  /etc/
RUN ls -la /etc/supervisor.d/
EXPOSE 80 443 69/udp 
CMD ["/usr/bin/supervisord",  "-c", "/etc/supervisord.conf"]

