# Frontend (React)
FROM node:14-alpine as build

WORKDIR /app

COPY ./package.json ./package-lock.json ./
RUN npm install

COPY ./ ./
RUN npm run build

# Serve the app using a lightweight server (Nginx or http-server)
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html

