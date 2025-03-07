
FROM node:20.18.3-alpine3.21 as build
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN npm run build


FROM node:20.18.3-alpine3.21
WORKDIR /app
COPY --from=build /app .
EXPOSE 3000
CMD ["npm", "start"]