FROM node:24-alpine3.22
WORKDIR /skill_test_1
COPY order-service/package.json order-service/package-lock.json* ./
RUN npm CI || npm install --production
COPY . .
ENV PORT=3002
EXPOSE 3002
CMD [ "node", "index.js" ]