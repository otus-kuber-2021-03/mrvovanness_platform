FROM docker.io/library/nginx:1.19
ARG WORKDIR=/app
ARG PORT=8000
ARG USER=1001

WORKDIR $WORKDIR

RUN echo " \n\
server { \n\
    listen       $PORT; \n\
    server_name  _; \n\
    location / { \n\
        root $WORKDIR; \n\
    } \n\
}" > /etc/nginx/conf.d/default.conf

RUN echo " \n\
<p>Hello from homework</p> \n\
" > homework.html

RUN chown -R $USER:$USER $WORKDIR /var/cache/nginx/ /var/run/

EXPOSE $PORT
USER $USER

