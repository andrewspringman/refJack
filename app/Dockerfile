FROM nginx:alpine
ADD https://api.github.com/repos/andrewspringman/jumpingJack/compare/master...HEAD /dev/null
WORKDIR /usr/share/nginx/html
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh && \
    echo GOT HERE 1 && \
    git clone --depth 1 https://github.com/andrewspringman/jumpingJack app && \
    echo GOT HERE 2 && \
    mv app/app/* . && \
    echo GOT HERE 3 && \
    rm -r -f app && \
    echo GOT HERE 4
