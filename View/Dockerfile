#front end docker file
FROM node:18-alpine AS build
WORKDIR /app
COPY edu-mentor/package*.json ./
RUN npm install
COPY edu-mentor ./
RUN npm run build

FROM node:18-alpine
WORKDIR /app
RUN npm install -g serve
COPY --from=build /app/build ./build
EXPOSE 3000
CMD ["serve", "-s", "build", "-l", "3000"]
