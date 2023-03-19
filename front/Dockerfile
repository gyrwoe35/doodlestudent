FROM node:16 as build

RUN apt-get -y update
RUN apt-get install -y git

RUN git clone https://github.com/barais/doodlestudent.git

WORKDIR /app
COPY package.json /app
COPY . /app

RUN npm install
RUN npm install -g @angular/cli@latest
RUN ng build

FROM nginx

COPY --from=build /app/dist/tlcfront /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
