#git 管理key
环境：linux
##1.生成公钥私钥

`ssh-keygen -t rsa -C "你的邮箱" -f ~/.ssh/起个文件名`

.ssh目录下会生成`你的文件名` `你的文件名.pub`

若要配置管理多个key，执行如上命令再起一个文件名

##2.配置
将新生成的ssh秘钥地址加入到ssh配置文件中`ssh-agent bash` `ssh-add ~/.ssh/你起的文件名`

确认是否加入成功`ssh-add -l`

在.ssh文件夹里添加config文件，如我要配置github

`
Host github.com
User w724883
HostName ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/github
Port 443 
`

因为github.com使用https协议所以需`HostName ssh.github.com` `Port 443 `

若config有权限问题`chmod 600 ~/.ssh/config`

若git仓库不是https协议，则config配置如

`
Host baidu.com
HostName baidu.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/icode
`

##3.公钥配置到git仓库
将`你起的文件名.pub`中的key复制到git仓库配置中，详情百度

##4.测试
测试是否成功`ssh -T git@github.com`

clone仓库`git clone 你的仓库地址`

若报SSL错误`git config --global http.sslVerify false`

若还有问题，请谷歌百度报错信息
