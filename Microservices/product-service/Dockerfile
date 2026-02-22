FROM node:24-alpine3.22

WORKDIR /app

COPY package.json package-lock.json* ./

RUN npm ci || npm install --production

COPY . .

ENV PORT=3001

EXPOSE 3001

CMD ["node", "app.js"]
