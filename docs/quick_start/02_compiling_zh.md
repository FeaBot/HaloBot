# 工程编译
## 1. 编译环境准备
### 1.1 安装VCOS Studio配置工具依赖插件
#### 1.1.1. Windows系统
1. 以【管理员权限】打开PowerShell，在根目录`haloosspace`下
2. 执行以下命令
    ```bash
    python ./vcos/vcos_studio/configurator/init_env.py -a
    ```
#### 1.1.2. Linux系统
1. 打开Linux终端，在根目录`haloosspace`下
2. 执行以下命令
    ```bash
    sudo apt update
    sudo apt install python3.8-venv libxcb-cursor0
    python ./vcos/vcos_studio/configurator/init_env.py -a
    ```
    > 在高版本的Ubuntu下如果Python3.8-venv找不到，请运行`sudo add-apt-repository ppa:deadsnakes/ppa`以添加 deadsnakes PPA源（用于提供旧版本 Python），然后再次运行上述命令
### 1.2. 安装编译工具链
在`haloosspace`目录，执行以下命令安装编译工具链：
```bash
python ./vcos/build/compiling_env.py
```
该命令依次执行以下安装步骤：
- 安装CMake工具，并将安装路径添加到PATH环境变量
- 安装kconfiglib工具
- 安装make工具，并设置`MAKE_TOOL_PATH`环境变量
- 安装ninja工具，并设置`NINJA_TOOL_PATH`环境变量
- 安装tricore-gcc编译工具链，并将安装路径添加到PATH环境变量
- 安装arm-gcc编译工具链，并将安装路径添加到PATH环境变量
- 安装Docker工具

## 2. 编译
### 2.1. 一键编译

> Windows系统需要以【管理员权限】打开PowerShell，并切换到`haloosspace`目录

- 切换到`haloosspace/build`目录：
  ```bash
  cd ./build
  ```
- 编译rt_demo应用：配置使用E3650_DEV_KIT板级配置，使用gcc编译器，使用make作为make工具，支持在实际开发板硬件运行
  ```bash
  python haloos_build.py -app_name rt_demo
  ```

  该命令会依次完成以下操作：

  - 根据 rt_demo 应用的 E3650_DEV_KIT 板级配置生成动态代码
  - 通过 CMake 调用 make 工具自动化构建
  - 最终编译生成镜像文件
  - 编译产物默认保存在 `haloosspace/output/rt_demo_E3650_DEV_KIT_gcc` 目录下

  > 如需编译 vbslite_demo，请将上述命令中的 -app_name rt_demo 替换为 -app_name vbslite_demo

### 2.2. 编译说明
详细的编译命令说明请参考[HaloOS编译框架说明](https://gitee.com/haloos/build/blob/master/README.md)

如果修改代码或新增代码目录并修改CMakeLists.txt文件，需要删除对应的output目录，重新执行编译命令

```bash
rm -r ./output  # 删除output目录
python haloos_build.py -app_name rt_demo  # 重新编译
```
