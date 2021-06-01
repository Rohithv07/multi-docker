FROM node:alpine as builder
WORKDIR '/app'
COPY ./packge.json ./
RUN yarn install
COPY . .
RUN yarn build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html












#try_files $uri $uri/ /index.html