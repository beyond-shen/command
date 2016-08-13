# Meteor 命令的操作


## 安装meteor
```
$ curl https://install.meteor.com/ | sh
```

## 创建一个项目
```
$ meteor create myapp
```

## 向meteor服务提交
```
$ meteor deploy *.meteor.com
username: smartx
password: ********
```
## 显示所有部署到服务器的域名
```bash
$  meteor list-sites
```

## 部署服务器
所有设置都在客户端这边完成, 然后通这命令去运程到服务器上进行自动安装软件和配置环境.


## 创建本地包
```bash
$ meteor create --package 包名
$ meteor add 包名
```

### 部署自己服务器上.
```bash
// ubuntu 64bit v14.04 LTS, 记得 update

$ npm -g install git+https://github.com/RockaLabs/meteor-up.git#muprockanew

$ muprockanew setup --config mupx.json

$ muprockanew deploy --config mupx.json
```

附上配置文件`mupx.json`
```text
{
  "servers": [
    {
      "host": "server_ip",
      "username": "root",
      //"pem": "~/.ssh/id_rsa",
    "password": "root user passwd"
    }
  ],

  "setupMongo": true,
  "appName": "mobileweb",
  "app": "~/mobile-web",          //网站文件存放的目录
  "env": {
    "PORT": 80,
    "ROOT_URL": "http://demo.plw.io"
  },

  "deployCheckWaitTime": 60,
  "enableUploadProgressBar": true
}
```
