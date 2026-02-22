FROM node:24-alpine3.22

WORKDIR /app

COPY package.json package-lock.json* ./

RUN npm ci || npm install --production

COPY . .

ENV PORT=3002

EXPOSE 3002

CMD ["node", "app.js"]
