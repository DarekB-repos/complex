FROM node:14.14.0-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
COPY . .
RUN npm install
RUN npm run build


FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/cong.d/default.conf
COPY --from=builder /app/build /user/share/nginx/html