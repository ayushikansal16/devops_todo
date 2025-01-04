# Build Stage
FROM node:18 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Production Stage
FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app ./
RUN npm install --production
CMD ["npm", "start"]
EXPOSE 3000
