# Source Code Download Process

## 1. Windows System
> **Note**: All PowerShell commands in this system must be executed with **Administrator privileges**. Installation may fail otherwise.

### 1.1. Install Python 3.8.10
> **Note**: Use Python version **3.8.10**, as HaloOS tools strongly depend on this version.

1. Download the [Python 3.8.10 official installer](https://www.python.org/ftp/python/3.8.10/python-3.8.10-amd64.exe) (x64 version by default). Ensure to check **"Add to Path"** during installation to add Python to your system's environment variables.

    > **Tip**: If multiple Python versions are installed, switch to 3.8.10.

2. Restart PowerShell and run `python --version`. If the output shows **3.8.10**, the installation was successful.

### 1.2. Install Git Repo Tool
Downloading the code requires both **git** and **git-repo**. If git is not installed, [download and install it](https://git-scm.com/downloads/win).

The git installation process is omitted here. The compilation process also requires git's patch tool. For Windows systems, add the patch tool path to the PATH environment variable:

1. Locate your git installation directory. The patch.exe is usually under `\usr\bin` (e.g., `C:\Program Files\Git\usr\bin`).
2. Press **Win + S** to search for **"Environment Variables"** → Select **"Edit system environment variables"**.
3. Under **"User variables"**, find **Path** → Click **"Edit"** → **"New"** → Add the patch path → Save.
4. Restart PowerShell with administrator privileges and run `patch --version`. A version number indicates successful installation.

Install **git-repo** as follows:

1. Download and extract the git-repo tool:
    1. [Download for Windows 32-bit](https://gitee.com/alibaba/git-repo-go/releases/download/v0.7.8/git-repo-0.7.8-Windows-32.zip)
    2. [Download for Windows 64-bit](https://gitee.com/alibaba/git-repo-go/releases/download/v0.7.8/git-repo-0.7.8-Windows-64.zip)

2. Copy the extracted `git-repo.exe` to your git installation's `cmd` directory (e.g., `C:\Program Files\Git\cmd`). This directory is typically added to the PATH during git installation. If not, follow steps 3–5 below.

3. Press **Win + S** to search for **"Environment Variables"** → Select **"Edit system environment variables"**.
4. Under **"User variables"**, find **Path** → Click **"Edit"** → **"New"** → Add the `cmd` path → Save.
5. Restart PowerShell and run the following commands. Version numbers indicate successful installation:
    ```PowerShell
    git --version      # Should display git version
    git-repo --version # Should display git-repo version
    ```

### 1.3. Download the Code

1. Generate/Add an SSH key. Follow the [Gitee SSH Key Setup Guide](https://gitee.com/help/articles/4181#article-header0).

2. Configure git:
    ```bash
    git config --global user.name "Replace with your name"
    git config --global user.email "Replace with your email"
    ```

3. Navigate to your desired code directory and run the following script to download the code:
    > **Tip**: Code will be placed in the `haloosspace` directory.

    ```bash
    mkdir haloosspace
    cd haloosspace
    rm -r ./.repo/  # Delete existing .repo directory if previous sync failed; skip this step if .repo doesn't exist
    git-repo init -u git@gitee.com:haloos/manifests.git -b master -m default.xml
    git-repo sync
    ```

    > For more `git-repo` commands, run `git-repo -h`.
example

    例子
    ```bash
    PS G:\Work\__HaloOS\haloosspace> git-repo init -u git@gitee.com:haloos/manifests.git -b master -m default.xml
    remote: Enumerating objects: 32, done.
    remote: Counting objects: 100% (32/32), done.
    remote: Compressing objects: 100% (32/32), done.
    remote: Total 32 (delta 14), reused 0 (delta 0), pack-reused 0 (from 0)
    Unpacking objects: 100% (32/32), 10.90 KiB | 7.00 KiB/s, done.
    From gitee.com:haloos/manifests
    * [new branch]      master     -> origin/master
    Note: switching to 'fd3b2f1e9f9ceba25fa0392062c55fec381d16d7'.

    You are in 'detached HEAD' state. You can look around, make experimental
    changes and commit them, and you can discard any commits you make in this
    state without impacting any branches by switching back to a branch.

    If you want to create a new branch to retain commits you create, you may
    do so (now or later) by using -c with the switch command. Example:

    git switch -c <new-branch-name>

    Or undo this operation with:

    git switch -

    Turn off this advice by setting config variable advice.detachedHead to false

    HEAD is now at fd3b2f1 vcos子系统二次开源，新增开源仓库
    Switched to a new branch 'default'
    NOTE: Your identity is: Kevin <kevin@feabot.com>
    NOTE: If you want to change this, please re-run 'git repo init' with --config-name
    NOTE: repo has been initialized in G:\Work\__HaloOS\haloosspace

    PS G:\Work\__HaloOS\haloosspace> git-repo sync
    remote: Enumerating objects: 208, done.
    remote: Enumerating objects: 27, done.
    remote: Enumerating objects: 94, done.
    remote: Counting objects: 100% (208/208), done.
    remote: Counting objects: 100% (27/27), done.
    remote: Compressing objects: 100% (27/27), done.
    remote: Enumerating objects: 24, done.
    remote: Enumerating objects: 13, done.
    remote: Counting objects:  30% (4/13)
    remote: Counting objects: 100% (24/24), done.
    remote: Compressing objects: 100% (24/24), done.
    remote: Total 24 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
    remote: Counting objects: 100% (13/13), done.
    remote: Compressing objects: 100% (13/13), done.
    remote: Counting objects:  30% (173/575)
    remote: Counting objects:  86% (495/575)
    remote: Counting objects: 100% (575/575), done.
    remote: Compressing objects: 100% (281/281), done.
    remote: Enumerating objects: 32, done.
    remote: Compressing objects: 100% (184/184), done.
    remote: Counting objects: 100% (33/33), done.
    remote: Compressing objects: 100% (30/30), done.
    remote: Counting objects: 100% (32/32), done.
    remote: Compressing objects: 100% (26/26), done.
    remote: Total 32 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
    remote: Total 27 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
    Unpacking objects: 100% (13/13), 8.88 KiB | 2.00 KiB/s, done.
    Unpacking objects:  51% (17/33), 9.01 KiB | 2.00 KiB/sFrom ssh://gitee.com/haloos/vcos_include
    * [new branch]      develop    -> origin/develop
    * [new branch]      master     -> origin/master KiB/siB/s
    remote: Total 208 (delta 60), reused 111 (delta 18), pack-reused 0 (from 0)Receiving objects:  97% (202/208), 15.52 MiB | 3.35 MiB/s
    Receiving objects: 100% (208/208), 16.19 MiB | 3.14 MiB/s, done.
    Resolving deltas: 100% (60/60), done. KiB | 0 bytes/siB/s
    remote: Total 33 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
    From ssh://gitee.com/haloos/docs 11.67 KiB | 2.00 KiB/s/s
    * [new branch]      develop    -> origin/develop
    * [new branch]      master     -> origin/master
    Unpacking objects: 100% (24/24), 11.65 KiB | 1024 bytes/s, done.
    From ssh://gitee.com/haloos/vcos_components | 27.00 KiB/s
    * [new branch]      develop    -> origin/develop
    * [new branch]      master     -> origin/master
    Unpacking objects: 100% (27/27), 154.95 KiB | 23.00 KiB/s, done.
    From ssh://gitee.com/haloos/tools_halo_trace
    * [new branch]      develop    -> origin/develop
    * [new branch]      master     -> origin/master
    Unpacking objects: 100% (33/33), 27.17 KiB | 3.00 KiB/s, done.
    ...
    
    If you want to create a new branch to retain commits you create, you may
    do so (now or later) by using -c with the switch command. Example:

    git switch -c <new-branch-name>

    Or undo this operation with:

    git switch -

    Turn off this advice by setting config variable advice.detachedHead to false

    HEAD is now at 92c1141 HaloOS init
    Updating files: 100% (23361/23361), done.
    Note: switching to 'df7a3d3dc12df5b8d257500c7dc15ceb6c77d542'.

    You are in 'detached HEAD' state. You can look around, make experimental
    changes and commit them, and you can discard any commits you make in this
    state without impacting any branches by switching back to a branch.

    If you want to create a new branch to retain commits you create, you may
    do so (now or later) by using -c with the switch command. Example:

    git switch -c <new-branch-name>

    Or undo this operation with:

    git switch -

    Turn off this advice by setting config variable advice.detachedHead to false

    HEAD is now at df7a3d3d 修复sim退出问题-zhangfengjiao@lixiang.com
    NOTE: Open HALOOS From LiXiang
    ```


## 2. Linux System (Ubuntu)

### 2.1. Install Python 3.8.10
> **Note**: Use Python version **3.8.10**, as HaloOS tools strongly depend on this version.

1. Install dependencies:
    ```bash
    sudo apt update && sudo apt install -y liblzma-dev libbz2-dev  libssl-dev build-essential zlib1g-dev libncurses5-dev  libgdbm-dev libnss3-dev  libreadline-dev  libffi-dev  libsqlite3-dev
    ```

2. Install and manage Python versions via `pyenv`:
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

3. If the output shows **Python 3.8.10**, the installation was successful.

### 2.2. Install Git Repo Tool
> Ubuntu usually includes git. Check with `git --version`. Install via `sudo apt install git` if necessary.

1. Install the `repo` tool:
    ```bash
    curl https://storage.googleapis.com/git-repo-downloads/repo > repo
    sudo chmod +x repo
    sudo mv repo /usr/bin  # Move repo to /usr/bin directory
    ```

2. Run `repo --version`. A version number indicates successful installation.

### 2.3. Download the Code

1. Generate/Add an SSH key. Follow the [Gitee SSH Key Setup Guide](https://gitee.com/help/articles/4181#article-header0).

2. Configure git:
    ```bash
    git config --global user.name "Replace with your name"
    git config --global user.email "Replace with your email"
    ```

3. Navigate to your desired code directory and run the following script to download the code:
    > **Tip**: Code will be placed in the `haloosspace` directory.

    ```bash
    mkdir haloosspace
    cd haloosspace
    rm -rf ./.repo/  # Delete existing .repo directory if previous sync failed; skip this step if .repo doesn't exist
    repo init -u git@gitee.com:haloos/manifests.git -b master -m default.xml
    repo sync
    ```

    > For more `repo` commands, run `repo -h`.