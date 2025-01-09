FROM node:12.4.0-alpine as build
WORKDIR /app
COPY package.json /app
RUN npm install --silent
COPY . /app
RUN npm run build

FROM nginx
COPY --from=build /app/build /usr/share/nginx/html
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]