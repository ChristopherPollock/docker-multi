FROM node:alpine as builder
RUN mkdir -p /app
WORKDIR '/app'
COPY package*.json ./
RUN npm install
COPY / ./
RUN npm run build

# /app/build <-- all the stuffwe care about for the next phase

FROM nginx
#not going to do anything on local desktop, but elasticbeanstalk pays attention to it
EXPOSE 3000
COPY .nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html