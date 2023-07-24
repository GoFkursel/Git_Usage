# **好习惯：上班前git pull，下班后git push**  
## 上传自己的项目->到远端  
### 如果是新文件夹需要执行2_creat_repo中的操作
1. 添加本地文件到缓存区  
   >git add .
2. 为上传文件添加注释  
   >git commit -m "first push"  
3. 提交本地文件到github新建项目中  
   >git push origin main  

***
**问题：error: src refspec main does not match any**  
**error: failed to push some refs to 'https://github.com/GoFkursel/Git_Usage.git'**
***
**解决**：1. 有可能是需要：  
>git remote add origin “url”  

2.好好看看git push origin xxx的分支名；（main，master傻傻分不清楚）
