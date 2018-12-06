# git

## 1、git实操

### ① 创建版本库

```spreadsheet
git  init()  --初始化
git config user.name "yrx"
git config user.email "yrx@qq.com"

--global 表示全局属性，所有的git项目都会共用属性（如果不想用全局的就把global去掉）
```

### ② 提交文件

```spreadsheet
1、查看文件状态：               		 
git  status  
2、将文件添加到暂存区：          			
git  add  文件名
3、提交文件到本地库（直接带注释提交）   		   
git  commit  –m “注释内容”


```

### ③ 查看文件提交记录

```spreadsheet
git log  文件名             					--查看历史记录
git log  --pretty=oneline 文件名				--简易信息查看

```

### ④ 回退历史

```spreadsheet
git  reset  --hard HEAD^                        --回退到上一次提交
git  reset  --hard HEAD~n  					   --回退n次操作
```

### ⑤ 版本穿越

```spreadsheet
git  reflog  文件名                           	 --查看历史记录的版本号
git  reset  --hard  版本号					    --执行可以到这个版本
```

### ⑥ 还原文件

```spreadsheet
git  checkout -- 文件名                           --还原文件（在本地将文件盖卵后可通过它来还原）
```

### ⑦ 删除某个文件

```spreadsheet
先删除文件
再git add 再提交
```

## 2、分支

### ① 创建分支

```spreadsheet
git  branch  <分支名>
git branch –v  查看分支
```

### ② 切换分支

```spreadsheet
git checkout  <分支名>
一步完成： git checkout  –b  <分支名>
```

### ③ 合并分支（改变谁，切换到谁上）

```spreadsheet
先切换到主干   git  checkout  master
git  merge  <分支名>
```

### 3、冲突办法

```spreadsheet
① 修改冲突文件（可通过git diff 找到冲突的文件及文件内容，再定位进去进行修改）

② git add 文件名

③ git commit
```



## 4、远程地址

### ① 增加远程地址

```spreadsheet
git remote add  <远端代号>   <远端地址> 
例：git  remote  add  origin  https://github.com/user111/Helloworld.git
```

### ② 推送到远程库

```spreadsheet
git  push   <远端代号>    <本地分支名称>。
例： git  push  origin  master

注：之前需要
git add         
git commit
```

### ③ 从远程仓库克隆

```spreadsheet
解释：克隆的默认远端代号为origin
git  clone   <远端地址>   <新项目目录名>。
例 git  clone  https://github.com/user111/Helloworld.git   hello_world
```

### ④ 从远程仓库更新项目

```spreadsheet
git  pull   <远端代号>   <远端分支名>。
例 git pull origin  master
```



## 5、如何邀请别人成为合作者

![](http://yinlingshishang.oss-cn-shenzhen.aliyuncs.com/%E5%9B%BE%E7%89%87%E4%B8%8A%E4%BC%A0/git/git_2018-12-05_21-05-08.png)

点击项目右上方的settings后出现如下情况，选择合作者后，git会给它邮箱发送消息，等待同意后即加入小组开发

## 6、协作冲突

> 在上传或同步代码时，由于你和他人都改了同一文件的同一位置的代码，版本管理软件无法判断究竟以谁为准，就会报告冲突,需要程序员手工解决。

解决冲突办法：

```spreadsheet
1、修改合并
2、git add 
3、git commit
```

