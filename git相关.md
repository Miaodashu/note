##git clone 克隆的东西过大 导致失败

以下是常见报错
``  

    git clone  https://example.com/example/example.git
    error: RPC failed; curl 18 transfer closed with outstanding read data remaining
    fatal: The remote end hung up unexpectedly
    fatal: early EOF
    fatal: index-pack failed

``
解决办法
1. 在第一次克隆的时候，把克隆深度设置为1
  git clone  https://example.com/example/example.git --depth  1
2. 修改host文件
    请在 ip.cn 查询域名 global-ssl.fastly.Net github.com
    windows修改host文件： C:\Windows\System32\drivers\etc\hosts
    linux 修改host文件： /etc/hosts

    151.101.41.194 github.global.ssl.fastly.net
    192.30.253.112 github.com

    这样会快很多

3. 亲测有效
    github下载受限问题
    ###在本机host文件加一下
>># Github
151.101.44.249 github.global.ssl.fastly.net 
192.30.253.113 github.com 
103.245.222.133 assets-cdn.github.com 
23.235.47.133 assets-cdn.github.com 
203.208.39.104 assets-cdn.github.com 
204.232.175.78 documentcloud.github.com 
204.232.175.94 gist.github.com 
107.21.116.220 help.github.com 
207.97.227.252 nodeload.github.com 
199.27.76.130 raw.github.com 
107.22.3.110 status.github.com 
204.232.175.78 training.github.com 
207.97.227.243 www.github.com 
185.31.16.184 github.global.ssl.fastly.net 
185.31.18.133 avatars0.githubusercontent.com 
185.31.19.133 avatars1.githubusercontent.com
    
