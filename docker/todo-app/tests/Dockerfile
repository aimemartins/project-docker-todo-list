FROM mjgargani/puppeteer:trybe1.0
WORKDIR /app
EXPOSE 3000
ADD node_modules.tar.gz ./todo-app/tests/
COPY . ./todo-app/tests/
CMD [ "npm", "test" ]
