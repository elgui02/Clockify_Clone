FROM node:20-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci --no-audit --no-fund
COPY . .
ENV CI=false
RUN npm run build

FROM nginx:alpine
# API_UPSTREAM = servicio backend dentro de Easypanel: http://<proyecto>_<servicio>:5000
ENV API_UPSTREAM=http://clockify_api:5000
COPY nginx.conf.template /etc/nginx/templates/default.conf.template
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
