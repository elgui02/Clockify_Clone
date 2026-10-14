# Para servidores con poca RAM: usa el build ya compilado en prebuilt/
# Regenerar prebuilt/: CI=false GENERATE_SOURCEMAP=false npm run build && rm -rf prebuilt && cp -r build prebuilt
# Build completo (requiere >2 GB RAM): usar Dockerfile.build
FROM nginx:alpine
ENV API_UPSTREAM=http://clockify_api:5000
COPY nginx.conf.template /etc/nginx/templates/default.conf.template
COPY prebuilt /usr/share/nginx/html
EXPOSE 80
