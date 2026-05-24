##### V1 #####
# FROM node:14

# RUN apt-get update
# WORKDIR /app
# COPY package*.json ./
# RUN npm install

# COPY . .
# EXPOSE 3000
# CMD [ "node", "server.js" ]


##### V2 #####
# Bước 1: Lấy image nền - Node.js version 14
FROM node:14-alpine
# Bước 2: Tạo thư mục làm việc bên trong container
WORKDIR /app
# Bước 3: Copy file package.json vào trước (để cache layer npm install)
COPY package*.json ./
# Bước 4: Cài dependencies
RUN npm install
# Bước 5: Copy toàn bộ source code vào container
COPY . .
# Bước 6: Khai báo port app sẽ chạy
EXPOSE 3000
# Bước 7: Lệnh chạy app khi container start
CMD ["node", "server.js"]