FROM nginx:alpine
RUN rm -rf /etc/nginx/conf.d/default.conf /etc/nginx/conf.d/nginx.conf
ADD nginx.conf.template /etc/nginx/conf.d/nginx.conf.template
WORKDIR /tmp
RUN wget https://github.com/ziahamza/webui-aria2/archive/master.zip -O - |unzip - && mv webui-aria2-master/docs /usr/share/nginx/webui && rm -rf webui-aria2-master
RUN wget https://github.com/mayswind/AriaNg-DailyBuild/archive/master.zip -O -|unzip - && mv AriaNg-DailyBuild-master /usr/share/nginx/ariang
ENV ARIA2_UI ariang
EXPOSE 80
CMD ["/bin/sh", "-c", "envsubst < /etc/nginx/conf.d/nginx.conf.template > /etc/nginx/conf.d/nginx.conf && nginx -g 'daemon off;'"]
