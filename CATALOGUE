FROM node:14 AS builder 
WORKDIR /opt/server
COPY package.json .
COPY server.js  .
RUN npm install

FROM node:14-alpine
WORKDIR /opt/server
COPY --from=builder /opt/server .
EXPOSE 8080
CMD [ "node", "server.js" ]