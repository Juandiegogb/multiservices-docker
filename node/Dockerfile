FROM node:alpine
WORKDIR /app
COPY package.json pnpm-lock.yaml ./
RUN npm i pnpm -g
RUN pnpm i
COPY ./dist ./dist
CMD ["pnpm", "run", "start:prod"]