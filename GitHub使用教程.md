# 1. 下载git并设置字体大小

![image-20241210192106834](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210192106834.png)

# 2. 配置用户名和邮箱

![image-20241210183618443](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210183618443.png)

```
git config --global user.name tantan180
```

```
git config --global user.email wentanw@foxmail.com
```

# 3. 从git上面下载代码，保存到本地

```
git clone 地址
```

- 地址从GitHub下载的代码那边复制
- .git文件生成并且不要动，其他工作区已经有了别人的代码，被我们剽窃过来了

# 4. 自己的文件上传到GitHub

打开要上传的文件，右击open git bash here，打开命令窗口，输入命令：

```
git init
```

这样就立即创建了一个.git的隐藏文件夹，不要动它。

![image-20241210193839203](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210193839203.png)

然后开始写代码，代码所在的地方叫做工作区，

# 5. 提交操作

```
git add .
```

![image-20241210193903171](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210193903171.png)

把所有文件和非空文件夹设置成准备提交状态

```
git commit -m "first test commit"
```

![image-20241210193916526](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210193916526.png)

备注一定要写，回车，代码就保存在仓库中了

# 6. 查看

```
git log
```

查看提交的历史记录

包括作者时间备注

![image-20241210193935665](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210193935665.png)

commit后面的一大串字符是提交的唯一字符号

# 6. 恢复

```
git checkout HEAD main.py
```

从最后一次提交里面把main.py复制到工作区覆盖

# 7. 按批次提交

```
git add main.py
git commit -m "main已完成"
git add 3.py
git commit -m "3已完成"
```

​	提交为准备状态在GitHub里面有个专业的术语，叫做提交到暂存区，这是GitHub特有的，版本管理软件中也不是必须要有这个功能，有利有弊吧，可能不太容易理解，但是在后续使用中会发现它的作用。SVN就没有暂存区这个概念

# 8. SSH的设置

打开GitHub，点击头像，SSH 安定GPG keys，标题自己写一个，密钥对的获取在下方：

打开命令行win+R

cmd,回车，打开命令窗口，输入指令：

```
ssh-keygen -t rsa -b 4096-C"注册的邮箱"
```

接下来会有几次询问，直接回车就可以

最后可以看到，在指定文件夹中生成了密钥对

![image-20241210195324310](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210195324310.png)

打开指定文件夹，选择pub文件，复制生成的密钥，粘贴到对应位置，添加完成，输入密码确认，OK

# 9. 测试SSH是否好用

```
ssh -T git@github.com
```

如果这里连接超时，就要手动找到hosts文件，打开输入GitHub的ip地址：140.82.113.4 github.com，保存好再次进行连接测试

可以看到连接成功

![image-20241210195649432](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210195649432.png)

# 10.远程上传地址 上传文件

```
git remote add orgin 地址
```

地址是GitHub上面的地址，选择SSH复制粘贴。

![image-20241210195915396](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210195915396.png)

# 11. 推送到仓库的master分支下

```
git push -u origin master
```

![image-20241210200037015](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241210200037015.png)

# 12. 回到github仓库刷新一下，切换到master分支，即可看到上传成功 的文件
