# GitLab Docker images

## 容器构建

docker build -t gitlab --rm .

## 运行

使用命令 `docker-compose up -d` 来启动。

## 替换正式环境

### 生成补丁文件

`diff -uNr /opt/gitlab/embedded/service/gitlab-rails/app app/ > ../zh_CN.diff`

### 打补丁

`patch -d /opt/gitlab/embedded/service/gitlab-rails/app/ -p1 < ../zh_CN.diff`

### 重启gitlab

`gitlab-ctl restart`


