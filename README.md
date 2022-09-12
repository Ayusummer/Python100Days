# Python100Days

[jackfrued/Python-100-Days: Python - 100天从新手到大师 (github.com)](https://github.com/jackfrued/Python-100-Days) 练手

233: [![wakatime](https://wakatime.com/badge/user/d8c0c428-5367-4918-aaf6-f3ecf4063899/project/b303890f-3330-4fac-b74a-bb34065e7b47.svg)](https://wakatime.com/badge/user/d8c0c428-5367-4918-aaf6-f3ecf4063899/project/b303890f-3330-4fac-b74a-bb34065e7b47)

---

# TODO
- [x] 写一版针对本仓库环境的 Quick Start Guide



# Quick Start Guide(Windows)

1. 拉取仓库源码
   
    ```bash
    git clone https://github.com/Ayusummer/Python100Days.git
    ```

2. 安装 VSCode 或者 Pycharm
   - VSCode
     - 安装插件
       - [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
       - [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
       - Gitmoji
       - Git Commit Lint
       - [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) / [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
       - wakatime
         - 可以先在 [Wakatime](https://wakatime.com/dashboard) 创建个账户, 然后在个人配置界面获取 `Secret API Key`, VSCode wakatime 插件安装完成会提示键入此项
         - 在启用 wakatime 插件并在该仓库写了一段时间的代码后就可以在 [Wakatime Dashboard](https://wakatime.com/dashboard) 看到统计数据了  
            点击对应的 `Project` 可以看到每个文件以及语言的统计数据, 右上角配置项中可以设置启用 `Project Badges` 并获取对应的 `Markdown` 代码, 然后在 `README.md` 中粘贴即可


3. 安装 [anaconda](#Anaconda) 和 [Poetry](#Poetry)
   - 配置 Poetry 虚拟环境在项目目录下生成
   - 创建一个 Python 3.8 版本或以上的 conda 环境并在当前命令行使用 `conda activate` 命令激活该 conda 环境
    > 或者这里不创建, 下面一步 Poetry 找不到已激活的也会在项目根目录下创建一个虚拟环境

4. 在项目根目录下执行 `poetry install` 安装依赖  
   > 在该步骤中, 若 poetry 找不到已激活的 3.8 版本以上的 Python 环境, 则会在项目根目录下创建一个虚拟环境  
   > 后续有新的包需要添加可以执行 `poetry add <package>` 命令来添加包  
   > 或者 `pyproject.toml` 文件有修改, 也可以执行 `poetry install` 来安装新增的依赖

5. 在 VSCode/Pycharm 中配置 Python 解释器为相应 conda 环境 / 项目根目录下的虚拟环境  

6. 查看相应天的文档并开始练习
    - 如果直接在 master 分支上练习, 请在每天练习完成后执行 `git pull && git add . && git commit -m "feat: dayXX && git push"` 来拉取仓库更新, 提交并推送代码
    - 如果新建分支并持续在此分支上练习的话, 可以   
        ```bash
        # 新建分支(以 test 为例)
        git checkout -b test
        # 修改代码后提交
        git add .
        git commit -m "feat: dayXX"
        # 发布分支(首次启用分支时执行此项)(如果IDE有提示发布分支的话也可以直接点击发布)
        git push origin test
        # 推送到远程仓库(非首次启用分支时执行此项)
        git push
        # 转移到 master 分支
        git checkout master
        # 拉取远程仓库更新
        git pull
        # 合并 test 分支
        git merge test
        # 推送到远程仓库
        git push
        # 返回 test 分支
        git checkout test
        # 合并对齐 master 分支
        git merge master
        # 推送到远程仓库
        git push
        ```



----

## Anaconda

> 需要注意的是, 使用 Anaconda Navigator 或者 conda 环境操作时需要关掉梯子, 否则可能会报 host 错误
> 

[安装包](https://ayusummer-my.sharepoint.com/:f:/g/personal/233_ayusummer_onmicrosoft_com/EhGEGFxHsINMtuhCpcUlQtUBRflV21xfYIkwpbeF2-d8IQ?e=Inh6dl)

> [Anaconda 官网](https://www.anaconda.com/products/individual)  
> 可在此处获取其他版本的安装包


> 需要注意的是 Anaconda 装完之后打开命令行总会自动进入 conda 环境, 可以通过更改 conda 配置来取消自动进入
>
> ```bash
> conda config --set auto_activate_base false
> ```
>
> 如果想要设置自动进入的话将 `false` 改为 `true` 运行即可
> 
安装完成后打开 `Anaconda Navigator`:

![image-20220523093633147](http://cdn.ayusummer233.top/img/202205230936469.png)

### Anaconda 换源

> [anaconda修改国内源 - 余者皆可 - 博客园 (cnblogs.com)](https://www.cnblogs.com/yuvejxke/p/13169172.html)
>
> [Anaconda 换国内源_scl52tg的博客-CSDN博客_conda 换源](https://blog.csdn.net/scl52tg/article/details/120959893)

- 打开 `anaconda prompt`   
  ![20220113131937](http://cdn.ayusummer233.top/img/20220113131937.png)  
  ![20220113132007](http://cdn.ayusummer233.top/img/20220113132007.png)

- 执行以下命令来配置清华源：

  > 不打开 navigator 也是完全可行的, 打开命令行就可以了, 前提是为 anaconda 配置了环境变量
  >
  > 只要在命令行中 `conda -V` 有版本号输出就可以了
  
  ```shell
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  conda config --set show_channel_urls yes
  ```
  
  配置清华源是为了后续使用 `pip` 命令安装 python 库时快些, 不配置换源而直接使用默认源的话在墙内容易超时报错
  
  > 中科大源:
  >
  > ```bash
  > conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
  > conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
  > conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
  > conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
  > conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
  > conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
  > conda config --set show_channel_urls yes
  > 
  > ```
  
  > 需要注意的是 conda 换源后会使更新 conda 的操作可能会报错
  >
  > 因此在更新 conda 的时候记得回复默认源
  >
  > ```bash
  > conda config --remove-key channels
  > ```
  >
  > 查看源:
  >
  > ```bash
  > conda config --show
  > ```
  >
  > ![image-20220804012242625](http://cdn.ayusummer233.top/img/202208040122840.png)

---

### 新建一个 conda 环境

#### Navigator

打开 `Anaconda Navigator -> Environments` 在环境列表底部按钮中找到 `Create` 并点击

![image-20220517153334579](http://cdn.ayusummer233.top/img/202205171533981.png)

为新环境命一个名(英文命名, 尽量简短些, 之后激活要用)

> 这里选择了 Python 3.8.13, 不上 3.9 或者 3.10 主要是因为有一些三方库更新没跟上, 不一定支持 python3.9 及以上

![image-20220517153442365](http://cdn.ayusummer233.top/img/202205171534732.png)

在命令行中使用 conda 环境可以使用如下指令激活:

```bash
conda activate 环境名
```

![image-20220517153733464](http://cdn.ayusummer233.top/img/202205171537691.png)

---
#### 命令行


创建一个名为 `BigData`, python 版本为 3.9 的虚拟环境

```shell
conda create -n BigData python=3.9
```

激活 `BigData` conda 环境

```shell
conda activate BigData
```

![20211219072053](http://cdn.ayusummer233.top/img/202208031558796.png)

退出当前虚拟环境
```shell
conda deactivate
```

> [Conda clean 净化Anaconda - 简书 (jianshu.com)](https://www.jianshu.com/p/f14ac62bef99)  
> [Anaconda conda常用命令：从入门到精通_chenxy_bwave的专栏-CSDN博客_conda常用命令](https://blog.csdn.net/chenxy_bwave/article/details/119996001)  


---

### Anaconda Navigator 升级

```bash
conda update conda -y
conda update anaconda -y
conda update anaconda-navigator -y
```

> 如果进行了换源操作记得在升级前恢复默认源, 否则可能会在镜像源中找不到更新包
>
> ```bash
> conda config --remove-key channels
> ```

---

## Poetry


> [Poetry - Python dependency management and packaging made easy (python-poetry.org)](https://python-poetry.org/)
>
> [python-poetry/poetry: Python dependency management and packaging made easy. (github.com)](https://github.com/python-poetry/poetry)

---

Poetry 是 Python 的依赖管理器

Poetry 可以帮助您声明、管理和安装 Python 项目的依赖项，确保到处都有正确的 stack。

支持 python 3.7 +

---

### 系统需求

需求 Python 2.7 或 3.5+. 支持跨平台, 在 Windows, Linux, OSX 系统上都可以同样出色地运行;

> Python 2.7  以及 3.5 后续版本不再支持, 需要升级 Python 版本   
> 个人建议 Python 3.8 以上, 因为用 Python 3.7.3 安装报错了

---

### 安装

> [Introduction | Documentation | Poetry - Python dependency management and packaging made easy (python-poetry.org)](https://python-poetry.org/docs/#windows-powershell-install-instructions)

---

Poetry 提供了一个自定义的安装程序, 通过解构 Poetry 的依赖关系, 将 Poetry 与系统的其他部分隔离开, 这是一种推荐的安装方式;


```powershell
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
```


![image-20220527065741632](http://cdn.ayusummer233.top/img/202205270657858.png)

> 上图中使用的是旧版的 `1.x` 版本的安装链接: `https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py`, 新版本推荐使用 `https://install.python-poetry.org` 来安装
>
> 建议在安装Python之前系统优先的Python不要是conda环境, 也就是说最好系统优先的 Python 环境是自己手动安装的标准 Python 环境
>
> PS: 因为我没装标准Python环境直接用 conda 出问题了, poetry 安装位置会乱飞还会找不到dll
>
> ![image-20220804101533439](http://cdn.ayusummer233.top/img/202208041015646.png)
>
> 使用 `poetry --version` 报错的话需要手动加下环境变量, 如上图所示的目录加到系统变量的 `path` 变量中即可
>
> ![image-20220804101836027](http://cdn.ayusummer233.top/img/202208041018136.png)
>
> ![image-20220804101729257](http://cdn.ayusummer233.top/img/202208041017345.png)
>
> ---
>
> ```powershell
> urllib.error.URLError: <urlopen error unknown url type: https>
> ```
>
> 如果出现以上错误, 那可能是因为默认 Python 版本比较低, 建议使用 3.8 以上的版本

poetry 会自动添加环境变量, 安装完后重启 `powershell`, 检查下 poetry 版本:

```powershell
poetry --version
```



![image-20220527070102934](http://cdn.ayusummer233.top/img/202205270701015.png)

---

### 配置文件

> [Configuration | Documentation | Poetry - Python dependency management and packaging made easy (python-poetry.org)](https://python-poetry.org/docs/configuration/)

---

- macOS: `~/Library/Application Support/pypoetry`
- Windows: `C:\Users\<username>\AppData\Roaming\pypoetry`

可以通过:

```powershell
poetry config virtualenvs.in-project true
```

来让 poetry 默认在项目根目录下创建 `venv` 作为虚拟环境目录, 或者直接写配置文件:

```toml
[virtualenvs]
in-project = true

```

> 此项配置默认为 `false`
>
> 若在配置此项之前创建了虚拟环境, windows 下应该在 `C:\Users\用户名\AppData\Local\pypoetry\Cache\virtualenvs` 目录下, 将其删除后重新在项目根目录下 `poetry install` 即可在项目根目录下创建 `.venv` 作为虚拟环境目录

--

#### 使用虚拟环境

默认情况下, poetry 会在 `{cache-dir}/virtualenvs` (`{cache-dir}\virtualenvs` on Windows)目录下创建一个虚拟环境:

![image-20220527074613612](http://cdn.ayusummer233.top/img/202205270746721.png)

如果先前设置了 `poetry config virtualenvs.in-project true` 的话执行 `poetry install` 安装依赖则会装在项目根目录的 `.venv` 里

激活虚拟环境: `cd` 进入 `.venv` 然后使用 `poetry shell` 激活虚拟环境

---

#### 结合 conda 环境使用

poetry 可以直接使用 conda 环境而不单独创建虚拟环境

只需要先 activate 对应 conda 环境, 然后把 `pyproject.toml` 中的 python 版本对其当前 conda 环境版本即可

此时使用 `poetry shell` 会输出 `Virtual environment already activated: xxxxxx`

不过当然也可以使用 conda 环境来创建虚拟环境, 只需要使用 `poetry env use 对应conda环境的python.exe路径` 即可利用该 conda 环境创建虚拟环境


### toml

#### 换源

> [The pyproject.toml file | Documentation | Poetry - Python dependency management and packaging made easy (python-poetry.org)](https://python-poetry.org/docs/pyproject/)

Poetry 默认配置从 PyPI 查询依赖包, 如果想要使用私仓(或是镜像)的话需要如如下配置

```toml
[[tool.poetry.source]]
name = "private"
url = "http://example.com/simple"
```

> 例如:
>
> ```toml
> [[tool.poetry.source]]
> name = "aliyun"
> url = "http://mirrors.aliyun.com/pypi/simple"
> default = true
> ```
>
> ```toml
> [[tool.poetry.source]]
> name = "tsinghua"
> url = "https://pypi.tuna.tsinghua.edu.cn/simple/"
> default = true
> ```

---
# VSCode 扩展建议

clone 完项目之后打开 VSCode 的扩展界面, 输入 @recommended, 会根据项目中的 `.vscode/extensions.json` 文件推荐扩展