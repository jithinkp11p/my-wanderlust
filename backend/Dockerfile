# stage 1
FROM node:21 as backend-Builder

WORKDIR /app

COPY . .

RUN npm i

# stage 2
FROM node:21-slim

WORKDIR /app

COPY --from=backend-Builder /app .

COPY .env.docker .env

EXPOSE 5000

CMD ["npm","start"]
