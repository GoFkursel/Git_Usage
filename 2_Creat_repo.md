# **好习惯：上班前git pull，下班后git push**  
## 新建一个仓库（Repo）并链接本地
1. 进入工作文件夹（working directory）  
   > git init #初始化一个本地仓库  
2. 首次与远程GitHub仓库连接（remote）  
   > git remote add origin <Github上的url>
3. 先拉下来远程仓库的文件（为保持版本内容一致）  
   > git pull origin main   
***
### *记录一下我初安装时遇到的问题：  
***
**1. fatal unable to access ‘httpsgithub.comxxxxxxxxxxx.git’ Recv failure Connection was reset**
***  
**解决**：1. 我首先关闭了我的VPN代理，发现没有用；   
2. 为了翻墙，进行如下设置:  
> git config --global -l #1.首先查看一下git内部的数据（我觉得没什么用）  
>  #先打开电脑“代理”->"手动设置代理"->"编辑"  
>  #查看IP后面的“端口”号，将此端口号代入进下面的“xxx”  
> git config --global http.proxy http://127.0.0.1:xxx  
> #一般来说可以不设置这个代理也可以访问到github，但是开了墙他会配置你本机的代理  
> #配置后，开启代理之后再访问如github这种外网他就会走这个端口进行访问，不在本地git中配置代理信息，最终就会报错
***  
**2. fatal: unable to access 'https://github.com/xxx/autowrite.git/':
Failed to connect to github.com port 443: Timed out**  
***  
**解决**：1.当前代理网速太慢，翻墙（成功）；  
2.因为git在拉取或者提交项目时，中间会有git的http和https代理，但是我们本地环境本身就有SSL协议了，所以取消git的https代理即可，不行再取消http的代理(没用过)；  
>//取消http代理  
>git config --global --unset http.proxy  
>//取消https代理   
>git config --global --unset https.proxy  
***
**3.To github.com:raxx/xxar.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'git@github.com:raxx/xxar.git'**
***  
**解决**：版本不一致，提交冲突，远端代码与本地代码不一致（别人在你提交之前提交了代码，导致你本地现在的代码与远端现在的代码不一致。）（但是，我是刚新建的，所以就是因为远端有一个README.md，我猜的）；  
**因此，需要先git pull origin main一下**，所以咱们就是说！标题！！！！很重要！

