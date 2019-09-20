FROM node:8 as builder

COPY ClientApp /ClientApp

WORKDIR /ClientApp

RUN npm i
RUN $(npm bin)/ng build

FROM nginx

COPY --from=builder /ClientApp/dist /usr/share/nginx/html

EXPOSE 80
