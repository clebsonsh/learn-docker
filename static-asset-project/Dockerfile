# build stage
FROM node:20 AS builder
WORKDIR /app
COPY package-lock.json package.json ./
RUN npm ci
COPY . .
RUN npm run build

# runtime stage
FROM nginx:stable-alpine
COPY --from=builder /app/build /usr/share/nginx/html

