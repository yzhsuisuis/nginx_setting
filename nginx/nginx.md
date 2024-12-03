docker container cp Nginx:/etc/nginx/nginx.conf D:/myProject/dev-ops/nginx/conf
docker container cp Nginx:/etc/nginx/conf.d/default.conf D:/myProject/dev-ops/nginx/conf/conf.d
docker container cp Nginx:/usr/share/nginx/html/index.html D:/myProject/dev-ops/nginx/html

docker run \
--name Nginx \
-p 80:80 \
-v D:/myProject/dev-ops/nginx/logs:/var/log/nginx \
-v D:/myProject/dev-ops/nginx/html:/usr/share/nginx/html \
-v D:/myProject/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf \
-v D:/myProject/dev-ops/nginx/conf/conf.d:/etc/nginx/conf.d \
-v D:/myProject/dev-ops/nginx/ssl:/etc/nginx/ssl/  \
--privileged=true -d --restart=always nginx

详细请看 dev-ops 第4节：Nginx环境配置