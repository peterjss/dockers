# build nginx with alpine
FROM alpine:latest

MAINTAINER peterjsss <peterjsss@gmail.com> 

RUN apk add --update nginx

COPY nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /run/nginx/ &&\
	echo "nginx" >>/etc/start.sh

EXPOSE 80

#CMD ["/bin/sh", "/etc/start.sh"]

CMD ["nginx", "-g", "daemon off;"]