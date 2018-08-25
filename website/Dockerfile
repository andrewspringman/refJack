FROM nginx:alpine
ADD https://api.github.com/repos/andrewspringman/jumpingJack/compare/master...HEAD /dev/null
WORKDIR /usr/share/nginx/html
RUN git clone --depth 1 https://github.com/andrewspringman/jumpingJack website
RUN mv website/website/* .
RUN rm -r -f website
