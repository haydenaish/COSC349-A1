FROM node:18-alpine

WORKDIR /react-files/


COPY public/ /react-files/public/
COPY src /react-files/src/
COPY package.json /react-files/

RUN npm install

EXPOSE 3000

CMD ["npm", "start"]
