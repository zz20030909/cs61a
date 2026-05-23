
#cs61a学习记录

目前写完lab05,hw03,projects cat


def a(b=0):
    b=b+1
    return b




python ok -q 函数 --local
测试代码
python ok  -u --local
python ok --score --local
本地测试题目
git使用
git add .
git commit -m ""
git status

git diff

git push

git pull <remote-name> <branch-name>

分支管理：git branch命令用于创建、列出、重命名和删除分支。 git branch <branch-name> git checkout <branch-name> git merge <branch-name> git branch -d <branch-name>

标签管理：git tag命令用于创建、查看和删除标签。 git tag -a <tag-name> -m "tag message" git show <tag-name> git tag -d <tag-name>





网络问题
PS C:\Users\86193\Desktop\新建文件夹\cs61a> git push
fatal: unable to access 'https://github.com/zz20030909/cs61a.git/': Recv failure: Connection was reset
解决方法？
修改上传代理，使用代理上传