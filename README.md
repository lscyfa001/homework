#my git test project

git init 先初始化本地仓库
git config --global user.name = 'xxx' git配置用户名
git conifg --global user.email = 'xxx' git配置邮箱
git add <-filename>  添加文件到本地仓库
        . 提交所有文件
        *.html 所有html文件
        xx 指定文件
git rm --cached <-filename> 删除add的文件

如果出现waring:warning:lf will be replaced by crlf in 'xxx'
CRLF -- Carriage-Return Line-Feed 回车换行
就是回车(CR, ASCII 13, \r) 换行(LF, ASCII 10, \n)。
这两个ACSII字符不会在屏幕有任何输出，但在Windows中广泛使用来标识一行的结束。而在Linux/UNIX系统中只有换行符。
也就是说在windows中的换行符为 CRLF， 而在linux下的换行符为：LF
使用git来生成一个rails工程后，文件中的换行符为LF， 当执行git add .时，系统提示：LF 将被转换成 CRLF

解决办法:
rm -rf .git
git config --global core.autocrlf false
然后重新 
git init
git add .

git status 查看本地仓库的提交情况
git commit 提交add的文件
git commit -m 'xxx提交时的注释和描述'

如果不需要上传的文件
touch .gitignore 创建gitignore文件，然后再文件内输入忽略的文件名/文件夹

git branch <-branchname>  git创建分支
git checkout <-branchname> 切换分支，在分支内提交的文件在master中看不到，形成一个局部空间，不影响主分支

分支代码commit后，切换回master分支，然后合并即可

git merge login 合并分支(需要切换会master分支) 

git remote add origin master https://xxxx  新建远程仓库的连接
git push -u origin master  然后开始提交本地仓库东西到远程仓库
git pull --rebase origin master 将远程仓库代码拷贝到本地
设置一次过后。再次提交了到本地仓库后 直接git push 不需要填写地址了
