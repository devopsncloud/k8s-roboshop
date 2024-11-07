FROM node:18.20.3-alpine3.19
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop 
WORKDIR /opt/server
#ENV MONGO=true #Removed to use it in kubernetes configMaps concept
RUN chown roboshop:roboshop /opt/server
USER roboshop
COPY package.json /opt/server/
COPY server.js  /opt/server/
RUN npm install
CMD [ "node","server.js" ]
