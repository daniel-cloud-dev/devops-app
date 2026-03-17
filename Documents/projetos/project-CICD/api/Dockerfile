FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install 

COPY . .

FROM node:18 AS runner

WORKDIR /app

COPY --from=builder /app ./

USER node
EXPOSE 3000
CMD [ "npm", "start" ]
