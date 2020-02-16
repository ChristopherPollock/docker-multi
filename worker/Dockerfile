FROM node:alpine

#Create app directory
RUN mkdir -p /app
WORKDIR '/app'

#  Install dependencies
COPY ./package.json ./
RUN npm install

#bundle app source
COPY ./ ./

#exports
CMD ["npm", "run", "start"]