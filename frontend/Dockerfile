FROM node:alpine as nodebuilder
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx
COPY --from=nodebuilder /app/build /usr/share/nginx/html