FROM nginx:1.11.10-alpine 

MAINTAINER mritd <mritd@mritd.me>

ENV TZ 'Asia/Shanghai'

RUN apk upgrade --no-cache \
    && apk add --no-cache bash git \
    && rm -rf /usr/share/nginx/html \ 
    && git clone https://github.com/mritd/k8s-repo-website.git /usr/share/nginx/html \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    && rm -rf /var/cache/apk/*

CMD ["nginx", "-g", "daemon off;"]