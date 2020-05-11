# syno-acme
通过acme协议更新群晖HTTPS泛域名证书的自动脚本

使用方法参见: [http://www.up4dev.com/2018/05/29/synology-ssl-wildcard-cert-update/](http://www.up4dev.com/2018/05/29/synology-ssl-wildcard-cert-update/)

参考了：
https://github.com/ferocknew/syno-acme/commit/0a47f7d9dede14a9180cd66b333b463a71b9ee75


### 修改默认证书

`/volume2/DDNS/syno-acme/cert-up.sh update`

### 还原
`/volume2/DDNS/syno-acme/cert-up.sh revert 20200511224813`

其中`20200511224813`是备份的文件夹的名称

### 自定义证书的目录使用

sudo -i

执行
`/volume2/DDNS/syno-acme/cert-up.sh update CTqjzd`
其中`CTqjzd`是自定义的目录，会在`/usr/syno/etc/certificate/_archive`创建一个目录，并把文件放在其中

之后（这一步可以自动之后可以用脚本自动完成）
`vim /usr/syno/etc/certificate/_archive/INFO`
参考其他加一条
```
"CTqjzd" : {
  "desc" : "秦晋之巅",
  "services" : []
},
```
