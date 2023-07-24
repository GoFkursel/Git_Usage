# **好习惯：上班前git pull，下班后git push**  
## 安装Git后首先与GitHub建立连接  
1. 在GitHub上新建仓库-> +New Repo...
2. 在终端配置Git基本信息（已经下载过Git的基础上）  
   >git config --global user.name "your name"  
   >
   >git config --global user.email "your_email@163.com"  
3. 在本地创建SSH key，并在工作文件夹下：
    >ssh-keygen -t rsa -C "your_email@163.com"  
4. 进入Users/wjw/.ssh文件夹下，有2个rsa..文件，打开rsa_pub文件，复制其中的内容；
5. 打开GitHub，进入Settings，在“SSH&GPG..”中新建一个公钥，起一个名字（没有要求），将刚刚复制的内容粘贴进去；  
6. 为了验证成功与否，在git bash下面（也就是终端）输入：  
   >ssh -T git@github.com  
   >#如果是第一次的会提示是否continue，输入yes就会看到：  
   >#You’ve successfully authenticated, but GitHub does not provide shell access。