FROM node:14-alpine
WORKDIR /app
EXPOSE 3001
ADD node_modules.tar.gz ./todo-app/back-end/
COPY . ./todo-app/back-end/
CMD [ "npm", "start" ]
