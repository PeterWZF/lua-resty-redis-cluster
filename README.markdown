Name
====

lua-resty-redis-cluster
the content is to be add.

下载完成后，只需要用到包中2个文件rediscluster.lua和redis_slot.c

.c文件无法在nginx配置文件中引入，需要编译成.so文件，编译命令： gcc SOURCE_FILES -fPIC -shared -o TARGET

如果执行编译命令报错，则需要先安装lua-devel
如果是离线安装，则需要先执行命令： rpm -qa lua  查看系统已安装的lua版本，再下载对应版本的lua-devel安装

安装完lua-devel之后，再前往 lualib目录下，执行命令:gcc redis_slot.c -fPIC -shared -o libredis_slot.so


如果你的redis集群需要密码验证，则不使用rediscluster.lua 而是用 rediscluster_auth.lua
