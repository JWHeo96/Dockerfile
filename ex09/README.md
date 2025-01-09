### 리액트 실행하기
npm start

### 리액트 빌드하기 (html 파일 만들기)
npm run build

### Dockerfile 만들어서 이미지 빌드하기
docker build . -t react-app

### nginx 실행하기
docker run -p 80:80 -dit react-app

```text
FROM node:12.4.0-alpine as build
WORKDIR /app
COPY package.json /app
RUN npm install --silent
COPY . /app
RUN npm run build

FROM nginx
COPY --from=build /app/build /usr/share/nginx/html
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
```