FROM debian:latest

RUN apt-get update
RUN apt-get install -y curl
RUN curl -sSL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs
RUN npm i -g gulp-cli
RUN curl -sSL https://github.com/googlecodelabs/tools/releases/download/v2.2.4/claat-linux-amd64 > /usr/local/bin/claat
RUN chmod 755 /usr/local/bin/claat 

ADD package.json /src/package.json
RUN cd /src && npm install 
ADD . /src

WORKDIR /src
EXPOSE 8000

CMD npm run serve