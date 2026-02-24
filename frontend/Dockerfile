FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install --legacy-peer-deps

COPY . .

# Reduce memory usage
ENV NODE_OPTIONS=--max_old_space_size=4096

RUN npm run build -- --configuration production

FROM nginx:alpine

COPY --from=build /app/dist/angular-15-crud/ /usr/share/nginx/html/

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]