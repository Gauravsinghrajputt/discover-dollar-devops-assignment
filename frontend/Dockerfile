# ---- BUILD STAGE ----
FROM node:18 as build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

RUN npm run build

# ---- NGINX STAGE ----
FROM nginx:latest

# Angular build output copy (AUTO WORKING METHOD)
COPY --from=build /app/dist/angular-15-crud/ /usr/share/nginx/html

EXPOSE 80
