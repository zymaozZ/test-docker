# Test web-app to use with Pluralsight courses and Docker Deep Dive book
# Linux x64
# 指令的作用是向镜像中添加新的程序或者文件 就会新建镜像层
# 指定基础镜像层
# apt 包管理器，加上 no-install-recommends （仅安装核心依赖）
FROM alpine

# 通过标签指定维护者
LABEL maintainer="nigelpoulton@hotmail.com"

# Install Node and NPM
RUN apk add --update nodejs nodejs-npm

# Copy app to /src
COPY . /src

# 为尚未执行的指定创建工作目录
WORKDIR /src

# Install dependencies (在之前设置的 WORKDIR 中执行)
RUN  npm install

EXPOSE 8080

# 指定当前镜像入口程序
ENTRYPOINT ["node", "./app.js"]
