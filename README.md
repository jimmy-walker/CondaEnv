#Conda
Actually, it makes sense to create a new environment for each larger project.
添加第三方库（能用conda用conda，不能用conda用pip），有一些库不论conda和pip都无法直接安装，只能下载.whl。
选择IDE（单文件Jupyter，项目组织开Pycharm）。

##整体流程

###1.查看
`conda list`查看当前环境下已安装的包
`conda env list`查看有哪些虚拟环境
`conda list -n py35`查看某个指定环境的已安装包，n表示name

###2.创建（新的开发环境会被默认安装在你conda目录下的envs文件目录下）
`conda create --name py35 python=3.5`创建一个名为py35的环境，指定Python版本是3.5（不用管是3.5.x，conda会为我们自动寻找3.5.x中的最新版本），其实--name可以用-n来代替

###3.复制环境
`conda create -n conda35 --clone root`

###4.切换分支
Linux, OS X: `source activate py35`
Windows: `activate py35`
切换回
Linux, OS X: `source deactivate`
Windows: `deactivate`

###5.安装软件
Finally you can install the desired packages:
`conda install numpy`
or, the whole anaconda:
`conda install anaconda`

###6.删除
`conda remove -n py35 --all`

##配置jupyter notebook
默认已经安装nb_conda
  直接在jupyter中kernel菜单切换即可。

##包管理（当版本不对时调试...）
`conda install -n conda35 numpy`安装package,如果不用-n指定环境名称，则被安装在当前活跃环境
`conda update -n conda35 numpy`更新package
`conda uninstall -n conda35 numpy` 删除package
