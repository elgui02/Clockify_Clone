# Para servidores con poca RAM: usa el build ya compilado en prebuilt/
# (regenerar con: CI=false GENERATE_SOURCEMAP=false npm run build && rm -rf prebuilt && cp -r build prebuilt)
FROM nginx:alpine
ENV API_UPSTREAM=http://clockify_api:5000
COPY nginx.conf.template /etc/nginx/templates/default.conf.template
COPY prebuilt /usr/share/nginx/html
EXPOSE 80
