# Build
FROM node:alpine as builder
WORKDIR /usr/app
COPY ./package.json .
RUN npm install
COPY . .
CMD ["npm", "run", "build"]

# Run
FROM node:alpine
WORKDIR /usr/app
COPY package.json ./
RUN npm install
COPY --from=builder /usr/app/dist .
CMD ["node", "server.js"]
