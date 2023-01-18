FROM node:14-alpine
WORKDIR /app
EXPOSE 3000
ADD node_modules.tar.gz ./todo-app/front-end/
COPY . ./todo-app/front-end/
CMD [ "npm", "start" ]

