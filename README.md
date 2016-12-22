# nvm
如果nvm正常使用，但在下载node时出错了，或者不动了，很可能就是被墙了或者国外镜像超时，可以切换到淘宝镜像

在nvm的安装路径下找到settings.txt打开:
 root: C:\nvm
 arch: 64
 proxy: none
 originalpath:
 originalversion:
 node_mirror:
 npm_mirror:
 
分别指定node和npm的mirror
 node_mirror: npm.taobao.org/mirrors/node/
 npm_mirror: npm.taobao.org/mirrors/npm/
