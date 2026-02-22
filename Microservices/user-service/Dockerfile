FROM node:24-alpine3.22
WORKDIR /skill_test_1
COPY gateway-service/package.json gateway-service/package-lock.json* ./
RUN npm CI || npm install --production
COPY . .
ENV PORT=3000
EXPOSE 3000
CMD [ "node", "index.js" ]