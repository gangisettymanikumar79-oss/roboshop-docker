FROM node:20.20.2-alpine3.22 AS builder
# this creates /app and move there
WORKDIR /app
COPY package.json .
COPY *.js .
# node_modules
RUN npm install



FROM node:20.20.2-alpine3.22 AS builder
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 8080
ENV MONGO="true" \
     MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]
















































