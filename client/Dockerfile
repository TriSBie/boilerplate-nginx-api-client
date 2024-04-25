FROM node:16-alpine as builder 
# as specific version of node to avoid bugs
WORKDIR /app
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html 
# copy from the previous stage, builder, and copy the build folder to the nginx folder