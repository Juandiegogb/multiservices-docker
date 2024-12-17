FROM node:alpine
WORKDIR /app
COPY package.json pnpm-lock.yaml ./
RUN npm i pnpm -g
RUN pnpm i
COPY .next/ .next/
COPY public ./public
CMD [ "pnpm" , "run" ,"start" ]