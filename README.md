# docker_muban

实例

version: '3.8'

services:
  my-service:
    image: xokksw4g0gssg448gwkgg4cw:07d07bae095fbac2f41eff33a86cf72329a2f489  # 使用你的镜像
    container_name: my_service      # 容器名称
    working_dir: /app_cp
    ports:
      - "30800:80"
    volumes:
      - ./local-app:/app_cp            # 将本地的 ./local-app 目录挂载到容器中的 /app 目录
    stdin_open: true                # 启用交互式输入
    tty: true                       # 分配伪终端
    entrypoint: ["sh"]
    command: 
        -c "cat cat /etc/os-release;php -v;php artisan serve --host=0.0.0.0 --port=80;"              # 启动 shell命令
        
