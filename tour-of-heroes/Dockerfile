FROM node

RUN apt-get update && apt-get upgrade -y \
    && apt-get clean

RUN npm install -g @angular/cli
RUN npm install --save-dev @angular-devkit/build-angular
RUN  npm install http-server -g

RUN mkdir /app
WORKDIR /app

COPY tour-of-heroes/package.json /app/
RUN npm install --only=production

COPY tour-of-heroes/dist /app/dist
#EXPOSE 4200
CMD  http-server -p 3000 -c-1 dist/tour-of-heroes