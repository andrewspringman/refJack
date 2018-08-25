FROM nginx:alpine
ADD https://api.github.com/repos/andrewspringman/jumpingJack/compare/master...HEAD /dev/null
WORKDIR /usr/share/nginx/html
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh && \
    git clone --depth 1 https://github.com/andrewspringman/jumpingJack app && \
    mv app/app/* . && \
    rm -r -f app
