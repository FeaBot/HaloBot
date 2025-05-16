# 源码下载流程
## 1. Windows系统
> 注意，本系统所有涉及PowerShell的指令，请通过【管理员权限】打开，否则安装可能失败
### 1.1. 安装Python 3.8.10
> 注意：请使用Python 3.8.10版本，HaloOS的工具强依赖于此版本

1. 下载[Python 3.8.10 官方安装包](https://www.python.org/ftp/python/3.8.10/python-3.8.10-amd64.exe)（默认为x64版本），安装的时候请注意勾选"Add to Path"，以添加到环境变量中

    > 提示：如果本机内有多个Python版本，请切换至3.8.10版本
2. 重启PowerShell，输入`python --version`，如果输出3.8.10版本，表示安装成功
### 1.2. 安装git repo工具
代码下载同时依赖git和git repo，如果没有安装git请 [下载并安装](https://git-scm.com/downloads/win)

git的安装流程此处略过，编译过程还需要使用git的patch工具，Windows系统需要将patch工具路径添加到PATH环境变量：
1. 找到git所在的安装路径，添加\usr\bin后就是patch.exe所在路径（例如：C:\Program Files\Git\usr\bin）
2. 按 Win + S 搜索 “环境变量” → 选择 “编辑系统环境变量”
3. 在 “用户变量” 中找到 Path → 点击 “编辑” → “新建” → 添加上述patch路径 → 保存
4. 用管理员权限重启PowerShell，执行`patch --version`，输出版本号即表示安装成功

git repo的安装流程如下：
1. 下载 git repo 工具并解压
    1. [Windows 32 位版本点此下载](https://gitee.com/alibaba/git-repo-go/releases/download/v0.7.8/git-repo-0.7.8-Windows-32.zip)
    2. [Windows 64 位版本点此下载](https://gitee.com/alibaba/git-repo-go/releases/download/v0.7.8/git-repo-0.7.8-Windows-64.zip)
2. 将解压后的git-repo.exe拷贝到git安装目录cmd路径下（如C:\Program Files\Git\cmd，注意该路径安装git时已经添加进环境变量，如果没有添加，需要执行以下步骤3~5）
3. 按 Win + S 搜索 “环境变量” → 选择 “编辑系统环境变量”
4. 在 “用户变量” 中找到 Path → 点击 “编辑” → “新建” → 添加上述cmd路径 → 保存
5. 重启 PowerShell 并运行以下命令，如果显示版本号即安装成功
    ```PowerShell
    git --version # 应输出版本信息  
    git-repo --version  # 应输出版本信息  
    ```
### 1.3. 下载代码
1. 生成/添加ssh密钥，请按[gitee ssh密钥添加流程](https://gitee.com/help/articles/4181#article-header0)进行
2. 配置git
    ```bash
    git config --global user.name "替换为您的名字"
    git config --global user.email "替换为您的邮箱"
    ```
3. 切换到您存放代码的目录下，运行如下脚本下载代码
    > 提示：这里将代码放在了haloosspace目录下

    ```bash
    mkdir haloosspace
    cd haloosspace
    rm -r ./.repo/  # 如此前有同步失败，需要先删除原有.repo目录；如果没有.repo目录，可以忽略此步骤
    git-repo init -u git@gitee.com:haloos/manifests.git -b master -m default.xml
    git-repo sync
    ```
    > 关于git repo的更多使用，可以输入`git-repo -h`查看

## 2. Linux系统（Ubuntu）
### 2.1. 安装Python 3.8.10
> 注意：请使用Python 3.8.10版本，HaloOS的工具强依赖于此版本
1. 安装依赖库
    ```bash
    sudo apt update && sudo apt install -y liblzma-dev libbz2-dev  libssl-dev build-essential zlib1g-dev libncurses5-dev  libgdbm-dev libnss3-dev  libreadline-dev  libffi-dev  libsqlite3-dev
    ```
2. 运行以下命令（通过pyenv安装并管理Python版本）
    ```bash
    curl https://pyenv.run | bash
    echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
    echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
    source ~/.bashrc
    pyenv install 3.8.10
    pyenv global 3.8.10
    python --version
    ```
3. 如果显示Python的版本号是3.8.10，即表示安装成功
### 2.2. 安装git repo工具
> Ubuntu通常会自带git工具，可以用`git --version`检查，如果未安装可以通过`sudo apt install git`命令安装

1. 运行以下命令安装repo工具
    ```bash
    curl https://storage.googleapis.com/git-repo-downloads/repo > repo
    sudo chmod +x repo
    sudo mv repo /usr/bin  # 将repo移动到/usr/bin目录下
    ```
2. 运行`repo --version`，显示版本号即安装成功
### 2.3. 下载代码
1. 生成/添加ssh密钥，请按[gitee ssh密钥添加流程](https://gitee.com/help/articles/4181#article-header0)进行
2. 配置git
    ```bash
    git config --global user.name "替换为您的名字"
    git config --global user.email "替换为您的邮箱"
    ```
3. 切换到您存放代码的目录下，运行如下脚本下载代码
    > 提示：这里将代码放在了haloosspace目录下

    ```bash
    mkdir haloosspace
    cd haloosspace
    rm -rf ./.repo/  # 如此前有同步失败，需要先删除原有.repo目录；如果没有.repo目录，可以忽略此步骤
    repo init -u git@gitee.com:haloos/manifests.git -b master -m default.xml
    repo sync
    ```

    > 关于repo的更多使用，可以输入`repo -h`查看