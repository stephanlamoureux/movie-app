# Stage 1 - the build process
FROM node:10 as builder
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .

# Stage 2 - the production environment
FROM node:10-alpine
WORKDIR /usr/src/app
COPY --from=builder /usr/src/app .
EXPOSE 3000
CMD [ "node", "index.js" ]
