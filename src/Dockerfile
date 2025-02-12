FROM ubuntu
ARG NODE_MAJOR=20
USER root
RUN apt-get update &&\
    apt-get install npm -y &&\
    apt-get install curl -y &&\
    apt-get install unzip -y &&\
    curl -o- https://fnm.vercel.app/install | bash &&\
    exec bash &&\
    fnm install ${NODE_MAJOR} -y 
WORKDIR /app
COPY . .
RUN npm install
ENTRYPOINT [ "node","server.js" ]