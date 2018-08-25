FROM nginx:alpine

#Ensure git only retreives new commits
ADD https://api.github.com/repos/andrewspringman/jumpingJack/compare/master...HEAD /dev/null

#We want to copy the files into this directory
WORKDIR /usr/share/nginx/html

#This image doesn't have git, so
#   Update and upgrade apk
#   Use apk to install git
#   Clone just the app directory
#   Move the app directory to where we are
#   Delete the excess files
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh && \
    git clone --depth 1 https://github.com/andrewspringman/jumpingJack website && \
    mv website/website/* . && \
    rm -r -f website
