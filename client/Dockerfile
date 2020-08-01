## Phase 1 DEV

FROM node:alpine

WORKDIR /app

COPY ./package.json ./

RUN npm install

COPY ./ ./

RUN npm run build

## Phase 2 PROD

FROM nginx

EXPOSE 3000

COPY ./nginx/defaut.conf /etc/nginx/conf.d/default.conf

COPY --from=0 /app/build /usr/share/nginx/html