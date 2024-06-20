FROM node:18-alpine AS installer
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
expose 3000
RUN npm run build
FROM nginx:latest As deployer
COPY --from=installer /app/build /usr/share/nginx/html

