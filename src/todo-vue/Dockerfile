FROM nginx:latest
LABEL maintainer 'Renato Matos'
WORKDIR /usr/share/nginx/html
COPY ./dist/css/* /usr/share/nginx/html/css/
COPY ./dist/js/* /usr/share/nginx/html/js/
COPY ./dist/favicon.ico .
COPY ./dist/index.html .
EXPOSE 80
