FROM nginx:alpine
ADD https://api.github.com/repos/andrewspringman/jumpingJack/compare/master...HEAD /dev/null
WORKDIR /usr/share/nginx/html
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh && \
    git clone --depth 1 https://github.com/andrewspringman/jumpingJack blog && \
    mv blog/blog/* . && \
    rm -r -f blog
