FROM node:12.16.1-alpine3.11 as builder
WORKDIR /app
COPY ./package.json ./
RUN yarn install
COPY ./ ./
RUN yarn build

FROM nginx:latest
COPY --from=builder /app/build /usr/share/nginx/html