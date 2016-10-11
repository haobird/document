##github使用说明

####github创建fork项目分支（Spoon-Knife项目举例）

1、创建指定项目的分支
登陆github，进入上述Spoon-Knife项目网址，点击右上角“Fork”按钮，稍等片刻便在自己的库中创建了项目的分支，
地址为https://github.com/myusername/Spoon-Knife.git

2、克隆项目到本地
执行如下命令
git clone https://github.com/username/Spoon-Knife.git
即在本地创建了一个项目的克隆。

3、配置本地库与原始库的关联
由于克隆后的本地库只有一个与自己的Github上的分支关联的名为origin的远程，所以要提交自己的更新到原始库，
必须配置与原始库https://github.com/octocat/Spoon-Knife的关联，名为upstream
执行如下：
cd Spoon-Knife #进入本地克隆的项目
git remote add upstream https://github.com/octocat/Spoon-Knife.git #添加与原始库的关联，名为upstream
git fetch upstream #从原始库上抓取最新更新

4、修改代码并提交PUSH

修改项目下的README文件做为测试，添加一行“first change”
git commit -a -m 'Update README'
git push origin master #提交push到远程自己的项目分支库
git fetch upstream #抓取远程原始库的更新
git merge upstream/master #将抓取的更新合并到本地的库中

5、发送Pull Requests
进入自己的Spoon-Knife分支库，点击右上角的“Pull Request” 按钮，进入发送Pull Request界面。
点击右上角“New pull request”按钮，进入新页面，上方左边是原始库，右边为自己的分支库，点击“Create pull request”按钮，在下方填写标题及评论。
点击“Send pull request”按钮，则Pull Request 发送成功。
然后就等原始库的维护人员审核，是否采用你的Pull Request，采用则你的代码更新会合并到原始库，完成代码贡献。



