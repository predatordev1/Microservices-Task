FROM node:24-alpine3.22
WORKDIR /skill_test_1
COPY product-service/package.json product-service/package-lock.json* ./
RUN npm CI || npm install --production
COPY . .
ENV PORT=3001
EXPOSE 3001
CMD [ "node", "index.js" ]