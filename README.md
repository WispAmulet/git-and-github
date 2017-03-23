# git-and-github
## 1. 如何使用git上传项目到github

1. **安装git客户端**

   [https://git-scm.com/](https://git-scm.com/)
  
2. **在github上创建一个repository**

   注意：名字最好为英文

3. **打开git客户端**

   首次登陆使用
   
       $ git config --global user.name "your user name" <br>
       $ git config --global user.email "your email address"
    
4. **设置SSH key**

   可以在C:\Users\your user name\\.ssh中找到SSH key，没有的话使用

       $ ssh-keygen -t rsa -C "your email address"    
   生成key。然后用记事本打开id_rsa.pub
    
5. **为github配置SSH key**

   Settings -> SSH and GPG keys -> New SSH key -> 将上一步id_rsa.pub中的文字复制到Key -> Add SSH key

6. **在本地创建项目目录**

7. **建立本地仓库**

   打开git界面使用 $ cd 命令切换到项目目录的地址或者直接在项目目录中右键 Git Bash Here
   
       $ git init
       项目中多了一个.git隐藏文件夹<br>
    
       $ git add .
       将所有文件添加到仓库<br>
    
       $ git commit -m "your commit"
       把文件提交到仓库

8. **关联github仓库**

   在之前创建的repo中找到SSH地址

       $ git remote add origin git@github.com:your ID/your repo name.git
    
9. **上传本地文件**

   使用git push命令

       $ git push -u origin master
       注意：空文件夹不会显示
  
10. **如何更新项目**

    在本地项目中创建一个文件，如 readme.txt

        $ git add readme.txt
        $ git commit -m "add a file"
        $ git push

- 其它

  git默认对文件大小写不敏感，使用

      $ git config core.ignorecase false

- 参考资料：

  [github入门到上传本地项目](http://blog.csdn.net/ch1451082329/article/details/52780175)  
  [如何配置Git支持大小写敏感和修改文件名中大小写字母](http://www.tuicool.com/articles/AnimaaE)


- 更多资料: 

  [廖雪峰的Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)  
  [Git学习版本回退和管理文件的修改及删除操作](https://my.oschina.net/u/1471093/blog/353710)  
  [Git删除暂存区或版本库中的文件](http://www.tuicool.com/articles/BJfUn2B)  
  [git commit -m 与 git commit -am 的区别](https://segmentfault.com/q/1010000005900988)  

## 2. 如何使用Markdown语言

- 参考资料：

  [Markdown: Basics （快速入门）](http://wowubuntu.com/markdown/basic.html)  
  [Markdown 语法说明 (简体中文版) ](http://wowubuntu.com/markdown/index.html)



