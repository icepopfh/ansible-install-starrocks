# ansible install starrocks 存算分离模式

## 部署后设置
`mysql -h <fe_address> -P <query_port:9030> -uroot`: 默认密码为空
### FE多个FOLLOWER节点
ALTER SYSTEM ADD FOLLOWER "x.x.x.x:9010";
ALTER SYSTEM ADD FOLLOWER "x.x.x.x:9010";
SHOW PROC '/frontends'\G

### 添加BE节点
ALTER SYSTEM ADD BACKEND "x.x.x.x:9050";
ALTER SYSTEM ADD BACKEND "x.x.x.x:9050";
ALTER SYSTEM ADD BACKEND "x.x.x.x:9050";
SHOW PROC '/backends'\G

### 设置root密码
SET PASSWORD = PASSWORD('password')