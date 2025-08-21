FROM node:18-alpine

WORKDIR /usr/src/app

# Copy package.json và pnpm-lock.yaml trước
COPY package*.json ./
COPY pnpm-lock.yaml* ./

# Cài pnpm
RUN npm install -g pnpm

# Đảm bảo NODE_ENV=development (để cài cả devDependencies)
ENV NODE_ENV=development

# Cài dependencies (cả devDependencies)
RUN pnpm install

# Copy toàn bộ source code
COPY . .

EXPOSE 50051

CMD ["pnpm", "start:dev"]
