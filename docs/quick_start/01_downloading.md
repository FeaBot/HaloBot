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