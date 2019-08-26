FROM alpine
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
RUN apk add --no-cache aria2
RUN mkdir /config && mkdir /data
VOLUME /config
VOLUME /data
EXPOSE 6800
EXPOSE 6881
EXPOSE 6882
CMD ['/usr/bin/aria2c','--conf-path','/config/aria2.conf']
