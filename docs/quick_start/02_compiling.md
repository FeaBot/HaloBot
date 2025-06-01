# Project Compilation

## 1. Prepare the Compilation Environment

### 1.1 Install Dependent Plugins for VCOS Studio Configuration Tool

#### 1.1.1 Windows System
1. Open PowerShell with **Administrator privileges** and navigate to the root directory `haloosspace`.
2. Execute the following command:
    ```bash
    python ./vcos/vcos_studio/configurator/init_env.py -a
    ```

Example
~~~bash
PS G:\Work\__HaloOS\haloosspace_new> python ./vcos/vcos_studio/configurator/init_env.py -a
非虚拟环境中运行: 创建虚拟环境并安装依赖...
创建虚拟环境到: G:\Work\__HaloOS\haloosspace_new\vcos\.venv
更新pip: G:\Work\__HaloOS\haloosspace_new\vcos\.venv\Scripts\pip.exe
Requirement already satisfied: pip in g:\work\__haloos\haloosspace_new\vcos\.venv\lib\site-packages (21.1.1)
Collecting pip
Using cached pip-25.0.1-py3-none-any.whl (1.8 MB)
Installing collected packages: pip
Attempting uninstall: pip
Found existing installation: pip 21.1.1
Uninstalling pip-21.1.1:
Successfully uninstalled pip-21.1.1
Successfully installed pip-25.0.1
安装依赖包: G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt
Ignoring durable-rules: markers 'sys_platform == "linux"' don't match your environment
Collecting ansi2html==1.9.1 (from -r G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt (line 1))
Using cached ansi2html-1.9.1-py3-none-any.whl.metadata (3.7 kB)
Collecting attrs==23.2.0 (from -r G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt (line 2))
Using cached attrs-23.2.0-py3-none-any.whl.metadata (9.5 kB)
Collecting bitstruct==8.19.0 (from -r G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt (line 3))
Using cached bitstruct-8.19.0-cp38-cp38-win_amd64.whl.metadata (7.6 kB)
Collecting cfile==0.2.0 (from -r G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt (line 5))
Using cached cfile-0.2.0-py3-none-any.whl.metadata (1.1 kB)
Collecting chardet==5.2.0 (from -r G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt (line 6))
Using cached chardet-5.2.0-py3-none-any.whl.metadata (3.4 kB)
Collecting diskcache==5.6.3 (from -r G:\Work\__HaloOS\haloosspace_new\vcos\vcos_studio\configurator\requirements.txt (line 7))
...
Using cached fonttools-4.57.0-cp38-cp38-win_amd64.whl (1.5 MB)
Using cached jsonschema_specifications-2023.12.1-py3-none-any.whl (18 kB)
Using cached kiwisolver-1.4.7-cp38-cp38-win_amd64.whl (55 kB)
Using cached numpy-1.24.4-cp38-cp38-win_amd64.whl (14.9 MB)
Using cached pillow-10.4.0-cp38-cp38-win_amd64.whl (2.6 MB)
Using cached pkgutil_resolve_name-1.3.10-py3-none-any.whl (4.7 kB)
Using cached pyparsing-3.1.4-py3-none-any.whl (104 kB)
Using cached python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
Using cached pywin32-310-cp38-cp38-win_amd64.whl (9.6 MB)
Using cached win32_setctime-1.2.0-py3-none-any.whl (4.1 kB)
Using cached beautifulsoup4-4.13.4-py3-none-any.whl (187 kB)
Using cached soupsieve-2.7-py3-none-any.whl (36 kB)
Installing collected packages: windows-curses, textparser, pywin32, pyserial, zipp, xmltodict, wrapt, win32-setctime, urllib3, typing-extensions, soupsieve, six, shiboken6, rpds-py, PyYAML, pyparsing, psutil, protobuf, pkgutil-resolve-name, pillow, packaging, numpy, msgpack, MarkupSafe, lxml, lark, kiwisolver, kconfiglib, jsonref, idna, fonttools, et-xmlfile, diskcache, cycler, coverage, colorama, charset-normalizer, chardet, cfile, certifi, bitstruct, attrs, ansi2html, requests, referencing, python-dateutil, python-can, PySide6-Essentials, openpyxl, loguru, Jinja2, importlib-resources, contourpy, beautifulsoup4, PySide6-Addons, matplotlib, jsonschema-specifications, bs4, PySide6, jsonschema
Successfully installed Jinja2-3.1.3 MarkupSafe-2.1.5 PySide6-6.6.3.1 PySide6-Addons-6.6.3.1 PySide6-Essentials-6.6.3.1 PyYAML-6.0.1 ansi2html-1.9.1 attrs-23.2.0 beautifulsoup4-4.13.4 bitstruct-8.19.0 bs4-0.0.2 certifi-2025.1.31 cfile-0.2.0 chardet-5.2.0 charset-normalizer-3.4.2 colorama-0.4.6 contourpy-1.1.1 coverage-7.3.2 cycler-0.12.1 diskcache-5.6.3 et-xmlfile-1.1.0 fonttools-4.57.0 idna-3.10 importlib-resources-6.4.0 jsonref-1.1.0 jsonschema-4.21.1 jsonschema-specifications-2023.12.1 kconfiglib-14.1.0 kiwisolver-1.4.7 lark-1.1.9 loguru-0.7.2 lxml-5.2.0 matplotlib-3.7.5 msgpack-1.0.8 numpy-1.24.4 openpyxl-3.1.2 packaging-24.0 pillow-10.4.0 pkgutil-resolve-name-1.3.10 protobuf-5.29.0 psutil-5.9.8 pyparsing-3.1.4 pyserial-3.5 python-can-4.3.2rc4 python-dateutil-2.9.0.post0 pywin32-310 referencing-0.35.0 requests-2.32.3 rpds-py-0.18.1 shiboken6-6.6.3.1 six-1.16.0 soupsieve-2.7 textparser-0.24.0 typing-extensions-4.11.0 urllib3-1.26.20 win32-setctime-1.2.0 windows-curses-2.3.2 wrapt-1.16.0 xmltodict-0.13.0 zipp-3.20.2
三方包安装成功
~~~

#### 1.1.2 Linux System
1. Open a Linux terminal and navigate to the root directory `haloosspace`.
2. Execute the following commands:
    ```bash
    sudo apt update
    sudo apt install python3.8-venv libxcb-cursor0
    python ./vcos/vcos_studio/configurator/init_env.py -a
    ```
    > If `python3.8-venv` is not found on newer Ubuntu versions, run `sudo add-apt-repository ppa:deadsnakes/ppa` to add the deadsnakes PPA (for older Python versions), then re-run the above commands.

### 1.2 Install the Compilation Toolchain
In the `haloosspace` directory, execute the following command to install the compilation toolchain:
```bash
python ./vcos/build/compiling_env.py
```
This command performs the following installation steps in sequence:
- Installs the CMake tool and adds its path to the PATH environment variable.
- Installs the kconfiglib tool.
- Installs the make tool and sets the `MAKE_TOOL_PATH` environment variable.
- Installs the ninja tool and sets the `NINJA_TOOL_PATH` environment variable.
- Installs the tricore-gcc compilation toolchain and adds its path to the PATH environment variable.
- Installs the arm-gcc compilation toolchain and adds its path to the PATH environment variable.
- Installs the Docker tool.

Example(windows)
~~~bash
 G:\Work\__HaloOS\haloosspace_new> python ./vcos/build/compiling_env.py

==============================
处理: 7z
==============================
开始下载: 7z2409-x64.exe
下载进度: 100.0% (1637343/1637343 bytes)
[OK] 下载完成: G:\Work\__HaloOS\haloosspace_new\.temp\7z2409-x64.exe

==============================
处理: CMake
==============================
开始下载: cmake-4.0.0-windows-x86_64.msi
下载进度: 100.0% (34242560/34242560 bytes)
[OK] 下载完成: G:\Work\__HaloOS\haloosspace_new\.temp\cmake-4.0.0-windows-x86_64.msi
[ERR] 安装失败:
1. 在CMake 4.0.0 官网安装包(https://github.com/Kitware/CMake/releases/download/v4.0.0/cmake-4.0.0-windows-x86_64.msi) 下载对应Windows版本的CMake工具
2. 双击安装，安装的时候请注意勾选'Add to Path'，以添加到环境变量中
3. 用管理员权限重启powershell，执行`cmake --version`，输出版本号即表示安装成功

==============================
处理: Ninja
==============================
开始下载: ninja-win.zip
下载进度: 100.0% (275425/275425 bytes)
[OK] 下载完成: G:\Work\__HaloOS\haloosspace_new\.temp\ninja-win.zip
[OK] 解压完成: ./ninja_temp
[OK] 已复制到系统目录: C:\Users\Administrator\bin\ninja.exe
[OK] 已设置环境变量 NINJA_TOOL_PATH=C:\Users\Administrator\bin (user级)

==============================
处理: Make
==============================
开始下载: make-3.81-bin.zip
下载进度: 100.0% (495645/495645 bytes)
[OK] 下载完成: G:\Work\__HaloOS\haloosspace_new\.temp\make-3.81-bin.zip
开始下载: make-3.81-dep.zip
下载进度: 100.0% (708206/708206 bytes)
[OK] 下载完成: G:\Work\__HaloOS\haloosspace_new\.temp\make-3.81-dep.zip
[OK] 解压完成: ./make_bin_temp
[OK] 已复制 make.exe 到 C:\Users\Administrator\bin
[OK] 解压完成: ./make_dep_temp
[OK] 已复制 libiconv2.dll 到 C:\Users\Administrator\bin
[OK] 已复制 libintl3.dll 到 C:\Users\Administrator\bin
[OK] 已设置环境变量 MAKE_TOOL_PATH=C:\Users\Administrator\bin (user级)

==============================
处理: Tricore GCC
==============================
正在克隆仓库: https://gitee.com/yanxiaoyong_1/tricore-gcc-win32
Cloning into './tricore-gcc-win32'...
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 5 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (5/5), 135.72 MiB | 9.40 MiB/s, done.
[OK] 仓库克隆完成: ./tricore-gcc-win32
正在解压: ./tricore-gcc-win32\tricore-gcc-win32.7z.001 -> C:\Users\Administrator\compiler

7-Zip 24.09 (x64) : Copyright (c) 1999-2024 Igor Pavlov : 2024-11-29

Scanning the drive for archives:
1 file, 52428800 bytes (50 MiB)

Extracting archive: .\tricore-gcc-win32\tricore-gcc-win32.7z.001
--
Path = .\tricore-gcc-win32\tricore-gcc-win32.7z.001
Type = Split
Physical Size = 52428800
Volumes = 3
Total Physical Size = 142269416
----
Path = tricore-gcc-win32.7z
Size = 142269416
--
Path = tricore-gcc-win32.7z
Type = 7z
Physical Size = 142269416
Headers Size = 18962
Method = LZMA2:24 BCJ
Solid = +
Blocks = 2

Everything is Ok

Folders: 202
Files: 1825
Size:       1283488136
Compressed: 142269416
[OK] 解压完成: C:\Users\Administrator\compiler
正在配置user级环境变量...
正在清理临时文件...

==============================
处理: ARM GCC
==============================
正在克隆仓库: https://gitee.com/yanxiaoyong_1/arm-gcc-win32
Cloning into './arm-gcc-win32'...
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (7/7), done.
remote: Total 7 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (7/7), 221.10 MiB | 8.01 MiB/s, done.
[OK] 仓库克隆完成: ./arm-gcc-win32
正在解压: ./arm-gcc-win32\arm-gcc-win32.7z.001 -> C:\Users\Administrator\compiler

7-Zip 24.09 (x64) : Copyright (c) 1999-2024 Igor Pavlov : 2024-11-29

Scanning the drive for archives:
1 file, 52428800 bytes (50 MiB)

Extracting archive: .\arm-gcc-win32\arm-gcc-win32.7z.001
--
Path = .\arm-gcc-win32\arm-gcc-win32.7z.001
Type = Split
Physical Size = 52428800
Volumes = 5
Total Physical Size = 231781972
----
Path = arm-gcc-win32.7z
Size = 231781972
--
Path = arm-gcc-win32.7z
Type = 7z
Physical Size = 231781972
Headers Size = 24408
Method = LZMA2:24 BCJ
Solid = +
Blocks = 2

Everything is Ok

Folders: 323
Files: 2700
Size:       1871626482
Compressed: 231781972
[OK] 解压完成: C:\Users\Administrator\compiler
正在配置user级环境变量...
正在清理临时文件...

=== 安装Python依赖 ===
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already satisfied: kconfiglib in c:\program files\python38\lib\site-packages (14.1.0)
WARNING: You are using pip version 21.1.1; however, version 25.0.1 is available.
You should consider upgrading via the 'c:\program files\python38\python.exe -m pip install --upgrade pip' command.

安装完成
~~~

## 2. Compilation

### 2.1 One-Click Compilation

> For Windows systems, open PowerShell with **Administrator privileges** and navigate to the `haloosspace` directory.

- Navigate to the `haloosspace/build` directory:
  ```bash
  cd ./build
  ```
- Compile the `rt_demo` application: Configure to use the E3650_DEV_KIT board configuration, gcc compiler, make as the build tool, and support running on actual development board hardware.
  ```bash
  python haloos_build.py -app_name rt_demo
  ```

  This command performs the following operations in sequence:
  - Generates dynamic code based on the E3650_DEV_KIT board configuration for the `rt_demo` application.
  - Automatically builds the project using CMake to invoke the make tool.
  - Generates the final image file.
  - The compilation output is saved by default in the `haloosspace/output/rt_demo_E3650_DEV_KIT_gcc` directory.

Example
  ```bash
G:\Work\__HaloOS\haloosspace_new\build> python haloos_build.py -app_name rt_demo
Start build with [rt_demo].
build real app name:  rt_demo
[Compiler] compiler [gcc] and path is [].
[32m2025-05-18 10:44:36.270[0m [[1mINFO[0m] [36mgenerate_cmd_func.py:46[0m - [1mLoading project file...[0m
[32m2025-05-18 10:44:36.270[0m [[1mINFO[0m] [36mgenerate_cmd_func.py:47[0m - [1mG:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\rt_demo.vcosproject[0m
[32m2025-05-18 10:44:36.341[0m [[1mINFO[0m] [36mvcos_version.py:199[0m - [1mINFO: All versions are compatible.[0m
[32m2025-05-18 10:44:36.355[0m [[33m[1mWARNING[0m] [36mproject_file_parser.py:346[0m - [33m[1mG:\Work\__HaloOS\haloosspace_new\drivers not exists, please do configuration in project_setting firstly[0m
[32m2025-05-18 10:44:36.355[0m [[1mINFO[0m] [36mproject_file_parser.py:351[0m - [1mG:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\log has been created which is not exists[0m
[32m2025-05-18 10:44:36.377[0m [[1mINFO[0m] [36mproject_file_parser.py:351[0m - [1mG:\Work\__HaloOS\haloosspace_new\apps\rt_demo\apps\asw_swc has been created which is not exists[0m
[32m2025-05-18 10:44:36.378[0m [[1mINFO[0m] [36mproject_file_parser.py:351[0m - [1mG:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\service_components has been created which is not exists[0m
[32m2025-05-18 10:44:37.150[0m [[1mINFO[0m] [36mcommon.py:177[0m - [1mCurrent chip does not have a separate system_cfg.json[0m
[32m2025-05-18 10:44:37.206[0m [[1mINFO[0m] [36mvalidator.py:200[0m - [1mstart validate with basic rule ==> module: NvM.[0m
[32m2025-05-18 10:44:37.208[0m [[1mINFO[0m] [36mvalidator.py:200[0m - [1mstart validate with basic rule ==> module: EcuC.[0m
[32m2025-05-18 10:44:37.209[0m [[1mINFO[0m] [36mvalidator.py:200[0m - [1mstart validate with basic rule ==> module: TcpIp.[0m
[32m2025-05-18 10:44:37.215[0m [[1mINFO[0m] [36mvalidator.py:200[0m - [1mstart validate with basic rule ==> module: EthIf.[0m
[32m2025-05-18 10:44:37.218[0m [[1mINFO[0m] [36mvalidator.py:200[0m - [1mstart validate with basic rule ==> module: Os.[0m
[32m2025-05-18 10:44:37.307[0m [[1mINFO[0m] [36mvalidator.py:200[0m - [1mstart validate with basic rule ==> module: Rte.[0m
[32m2025-05-18 10:44:37.333[0m [[1mINFO[0m] [36mvalidator.py:146[0m - [1mstart validate with semantic rule ==> module: NvM.[0m
[32m2025-05-18 10:44:37.334[0m [[1mINFO[0m] [36mvalidator.py:146[0m - [1mstart validate with semantic rule ==> module: EcuC.[0m
[32m2025-05-18 10:44:37.335[0m [[1mINFO[0m] [36mvalidator.py:146[0m - [1mstart validate with semantic rule ==> module: TcpIp.[0m
[32m2025-05-18 10:44:37.335[0m [[1mINFO[0m] [36mvalidator.py:146[0m - [1mstart validate with semantic rule ==> module: EthIf.[0m
[32m2025-05-18 10:44:37.335[0m [[1mINFO[0m] [36mvalidator.py:146[0m - [1mstart validate with semantic rule ==> module: Os.[0m
[32m2025-05-18 10:44:37.336[0m [[1mINFO[0m] [36mvalidator.py:146[0m - [1mstart validate with semantic rule ==> module: Rte.[0m
[32m2025-05-18 10:44:37.340[0m [[1mINFO[0m] [36mvalidator.py:182[0m - [1mNvM module validate successful[0m
[32m2025-05-18 10:44:37.347[0m [[1mINFO[0m] [36mvalidator.py:182[0m - [1mEcuC module validate successful[0m
[32m2025-05-18 10:44:37.365[0m [[1mINFO[0m] [36mvalidator.py:182[0m - [1mTcpIp module validate successful[0m
[32m2025-05-18 10:44:37.393[0m [[1mINFO[0m] [36mvalidator.py:182[0m - [1mEthIf module validate successful[0m
[32m2025-05-18 10:44:37.393[0m [[1mINFO[0m] [36mvalidator.py:182[0m - [1mOs module validate successful[0m
[32m2025-05-18 10:44:37.516[0m [[1mINFO[0m] [36mvalidator.py:182[0m - [1mRte module validate successful[0m
[32m2025-05-18 10:44:37.516[0m [[1mINFO[0m] [36mvalidator.py:110[0m - [1mfinish validation![0m
[32m2025-05-18 10:44:37.518[0m [[1mINFO[0m] [36mgenerator.py:112[0m - [1mStart the code generator of the rt_demo![0m
[32m2025-05-18 10:44:37.518[0m [[1mINFO[0m] [36mgenerator.py:113[0m - [1mGeneration list : ['EthIf', 'MemIf', 'NvM', 'Os', 'Rte', 'TcpIp'][0m
[32m2025-05-18 10:44:37.614[0m [[1mINFO[0m] [36mgenerator.py:135[0m - [1mGeneration list : ['EthIf', 'MemIf', 'NvM', 'Os', 'Rte', 'TcpIp'][0m
[32m2025-05-18 10:44:37.674[0m [[1mINFO[0m] [36mgenerator.py:391[0m - [1mFinish generating Rte_Type.h file[0m
[32m2025-05-18 10:44:37.674[0m [[1mINFO[0m] [36mgenerator.py:238[0m - [1mFinish generating Rte_SystemApplication_Core0.h file[0m
[32m2025-05-18 10:44:37.675[0m [[1mINFO[0m] [36mgenerator.py:238[0m - [1mFinish generating Rte_SystemApplication_Core1.h file[0m
[32m2025-05-18 10:44:37.675[0m [[1mINFO[0m] [36mgenerator.py:238[0m - [1mFinish generating Rte_SystemApplication_Core2.h file[0m
[32m2025-05-18 10:44:37.675[0m [[1mINFO[0m] [36mgenerator.py:238[0m - [1mFinish generating Rte_SystemApplication_Core3.h file[0m
[32m2025-05-18 10:44:37.678[0m [[1mINFO[0m] [36mgenerator.py:253[0m - [1mFinish generating Rte_SystemApplication_Core0.c file[0m
[32m2025-05-18 10:44:37.679[0m [[1mINFO[0m] [36mgenerator.py:253[0m - [1mFinish generating Rte_SystemApplication_Core1.c file[0m
[32m2025-05-18 10:44:37.680[0m [[1mINFO[0m] [36mgenerator.py:253[0m - [1mFinish generating Rte_SystemApplication_Core2.c file[0m
[32m2025-05-18 10:44:37.681[0m [[1mINFO[0m] [36mgenerator.py:253[0m - [1mFinish generating Rte_SystemApplication_Core3.c file[0m
[32m2025-05-18 10:44:37.681[0m [[1mINFO[0m] [36mgenerator.py:301[0m - [1mFinish generating Rte_Main.h file[0m
[32m2025-05-18 10:44:37.682[0m [[1mINFO[0m] [36mgenerator.py:270[0m - [1mFinish generating Rte.c file[0m
[32m2025-05-18 10:44:37.682[0m [[1mINFO[0m] [36mgenerator.py:280[0m - [1mFinish generating Rte.h file[0m
[32m2025-05-18 10:44:37.683[0m [[1mINFO[0m] [36mgenerator.py:441[0m - [1mFinish generating Rte_Cbk.h file[0m
[32m2025-05-18 10:44:37.683[0m [[1mINFO[0m] [36mgenerator.py:462[0m - [1mFinish generating SchM_NvM.h file[0m
[32m2025-05-18 10:44:37.684[0m [[1mINFO[0m] [36mgenerator.py:462[0m - [1mFinish generating SchM_EthIf.h file[0m
[32m2025-05-18 10:44:37.684[0m [[1mINFO[0m] [36mgenerator.py:462[0m - [1mFinish generating SchM_TcpIp.h file[0m
[32m2025-05-18 10:44:37.685[0m [[1mINFO[0m] [36mgenerator.py:478[0m - [1mFinish generating SchM_NvM_Type.h file[0m
[32m2025-05-18 10:44:37.685[0m [[1mINFO[0m] [36mgenerator.py:478[0m - [1mFinish generating SchM_EthIf_Type.h file[0m
[32m2025-05-18 10:44:37.686[0m [[1mINFO[0m] [36mgenerator.py:478[0m - [1mFinish generating SchM_TcpIp_Type.h file[0m
[32m2025-05-18 10:44:37.686[0m [[1mINFO[0m] [36mgenerator.py:317[0m - [1mFinish generating Rte_Hook_Rtm.c file[0m
[32m2025-05-18 10:44:37.687[0m [[1mINFO[0m] [36mgenerator.py:333[0m - [1mFinish generating Rte_Hook.h file[0m
[32m2025-05-18 10:44:37.703[0m [[1mINFO[0m] [36mgenerator.py:130[0m - [1mFinish generating ethif_cfg.h file[0m
[32m2025-05-18 10:44:37.710[0m [[1mINFO[0m] [36mgenerator.py:105[0m - [1mFinish generating ethif_eth_callout.c file[0m
[32m2025-05-18 10:44:37.710[0m [[1mINFO[0m] [36mgenerator.py:118[0m - [1mFinish generating ethif_eth_callout.h file[0m
[32m2025-05-18 10:44:37.733[0m [[1mINFO[0m] [36mgenerator.py:130[0m - [1mFinish generating ethif_lcfg.c file[0m
[32m2025-05-18 10:44:37.734[0m [[1mINFO[0m] [36mgenerator.py:130[0m - [1mFinish generating ethif_lcfg.h file[0m
[32m2025-05-18 10:44:37.743[0m [[1mINFO[0m] [36mgenerator.py:51[0m - [1mFinish generating memif_cfg.h file[0m
[32m2025-05-18 10:44:37.745[0m [[1mINFO[0m] [36mgenerator.py:58[0m - [1mFinish generating memif_cfg.c file[0m
[32m2025-05-18 10:44:37.765[0m [[1mINFO[0m] [36mgenerator.py:83[0m - [1mFinish generating nvm_user_callout.c file[0m
[32m2025-05-18 10:44:37.769[0m [[1mINFO[0m] [36mgenerator.py:90[0m - [1mFinish generating nvm_cfg.h file[0m
[32m2025-05-18 10:44:37.776[0m [[1mINFO[0m] [36mgenerator.py:97[0m - [1mFinish generating nvm_cfg.c file[0m
[32m2025-05-18 10:44:37.797[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating task_cfg.h file[0m
[32m2025-05-18 10:44:37.804[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating task_cfg.c file[0m
[32m2025-05-18 10:44:37.806[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating stack_cfg.h file[0m
[32m2025-05-18 10:44:37.810[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating application_cfg.h file[0m
[32m2025-05-18 10:44:37.810[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating application_cfg.c file[0m
[32m2025-05-18 10:44:37.810[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating core_cfg.c file[0m
[32m2025-05-18 10:44:37.810[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating core_cfg.h file[0m
[32m2025-05-18 10:44:37.810[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating ipicall_cfg.c file[0m
[32m2025-05-18 10:44:37.825[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating ipicall_cfg.h file[0m
[32m2025-05-18 10:44:37.825[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating isr_cfg.c file[0m
[32m2025-05-18 10:44:37.825[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating isr_cfg.h file[0m
[32m2025-05-18 10:44:37.825[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating spinlock_cfg.h file[0m
[32m2025-05-18 10:44:37.841[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating spinlock_cfg.c file[0m
[32m2025-05-18 10:44:37.841[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating event_cfg.h file[0m
[32m2025-05-18 10:44:37.841[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating schedtable_cfg.h file[0m
[32m2025-05-18 10:44:37.861[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating schedtable_cfg.c file[0m
[32m2025-05-18 10:44:37.865[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating os_compiler_cfg.h file[0m
[32m2025-05-18 10:44:37.869[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating counter_cfg.h file[0m
[32m2025-05-18 10:44:37.875[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating counter_cfg.c file[0m
[32m2025-05-18 10:44:37.889[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating tcpip_memmap.h file[0m
[32m2025-05-18 10:44:37.890[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating ethif_memmap.h file[0m
[32m2025-05-18 10:44:37.890[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating eth_memmap.h file[0m
[32m2025-05-18 10:44:37.890[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating crc_memmap.h file[0m
[32m2025-05-18 10:44:37.891[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating nvm_memmap.h file[0m
[32m2025-05-18 10:44:37.891[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating memif_memmap.h file[0m
[32m2025-05-18 10:44:37.892[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating rte_memmap.h file[0m
[32m2025-05-18 10:44:37.893[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating memmap.h file[0m
[32m2025-05-18 10:44:37.893[0m [[1mINFO[0m] [36mgenerator.py:48[0m - [1mFinish generating memmap_int.h file[0m
[32m2025-05-18 10:44:37.909[0m [[1mINFO[0m] [36mgenerator.py:51[0m - [1mFinish generating tcpip_cfg.h file[0m
[32m2025-05-18 10:44:37.911[0m [[1mINFO[0m] [36mgenerator.py:59[0m - [1mFinish generating tcpip_lcfg.h file[0m
[32m2025-05-18 10:44:37.920[0m [[1mINFO[0m] [36mgenerator.py:67[0m - [1mFinish generating tcpip_cfg.c file[0m
[32m2025-05-18 10:44:37.932[0m [[1mINFO[0m] [36mgenerator.py:77[0m - [1mFinish generating Lwip_Cfg.h file[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:85[0m - [1mFinish generating Lwippool_Cfg.h file[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:255[0m - [1mRte module generate c code successful[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:255[0m - [1mEthIf module generate c code successful[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:255[0m - [1mMemIf module generate c code successful[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:255[0m - [1mNvM module generate c code successful[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:255[0m - [1mOs module generate c code successful[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:255[0m - [1mTcpIp module generate c code successful[0m
[32m2025-05-18 10:44:37.934[0m [[1mINFO[0m] [36mgenerator.py:151[0m - [1mFinish the code generator of the rt_demo[0m
[32m2025-05-18 10:44:37.953[0m [[1mINFO[0m] [36mgenerate_cmd_func.py:73[0m - [1mStart saving arxml ...[0m
[32m2025-05-18 10:44:37.954[0m [[1mINFO[0m] [36mproject_file_parser.py:119[0m - [1mpath of {'user_plugin_output_path'} not existed[0m
[32m2025-05-18 10:44:37.954[0m [[1mINFO[0m] [36mproject_file_parser.py:119[0m - [1mpath of {'compiler_path'} not existed[0m
[32m2025-05-18 10:44:37.954[0m [[1mINFO[0m] [36mproject_file_parser.py:119[0m - [1mpath of {'mcal_path'} not existed[0m
[32m2025-05-18 10:44:37.954[0m [[1mINFO[0m] [36mproject_file_parser.py:119[0m - [1mpath of {'mcal_gendata_path'} not existed[0m
[32m2025-05-18 10:44:37.961[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\NvM\NvM_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:37.963[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\MemIf\MemIf_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:37.968[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\EcuC\EcuC_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:37.980[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\TcpIp\TcpIp_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:37.987[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\EthIf\EthIf_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:38.226[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\Os\Os_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:38.242[0m [[1mINFO[0m] [36marxml_parse_save.py:741[0m - [1msave G:\Work\__HaloOS\haloosspace_new\apps\rt_demo\platform_cfg\e3650_cfg\config\bsw\Rte\Rte_ecuc.arxml succeeded[0m
[32m2025-05-18 10:44:38.276[0m [[1mINFO[0m] [36mvalidator.py:374[0m - [1mSave ignored log to G:/Work/__HaloOS/haloosspace_new/apps/rt_demo/platform_cfg/e3650_cfg/config/system/ignored_logs.log[0m
[32m2025-05-18 10:44:38.277[0m [[1mINFO[0m] [36mvalidator.py:342[0m - [1mSave validation log to G:/Work/__HaloOS/haloosspace_new/apps/rt_demo/platform_cfg/e3650_cfg/config/system/validation_logs.log[0m
[32m2025-05-18 10:44:38.277[0m [[1mINFO[0m] [36mgenerate_cmd_func.py:78[0m - [1mFinish saving arxml ...[0m
[32m2025-05-18 10:44:38.278[0m [[1mINFO[0m] [36mauto_cli.py:92[0m - [1mAutoCli successfully[0m
[rt_demo:E3650_DEV_KIT][codegen] End.
[Compiler] compiler [gcc] and path is [].
[rt_demo:E3650_DEV_KIT] gendate_cmake: cmake -B G:/Work/__HaloOS/haloosspace_new/vcos/../output/rt_demo_E3650_DEV_KIT_gcc -DBOARD_CONFIG=G:/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/boards/E3650_DEV_KIT/configs/vcos_gcc -DAPPS_DIR=vcos_examples/rt_demo                     -G "MinGW Makefiles" -DWIN32=1 -DCMAKE_MAKE_PROGRAM="make.exe" -DBOARD_NAME=E3650_DEV_KIT
-- Initializing NuttX
--   ENV{PROCESSOR_ARCHITECTURE} = AMD64
Select HOST_WINDOWS=y
Select WINDOWS_NATIVE=y
--   CMake   4.0.0
--   Board:  E3650_DEV_KIT
--   Config: vcos_gcc
--   Appdir: G:/Work/__HaloOS/haloosspace_new/vcos/apps
-- The C compiler identification is GNU 11.3.0
-- The CXX compiler identification is GNU 11.3.0
-- The ASM compiler identification is GNU
-- Found assembler: C:/Users/Administrator/compiler/arm-gcc-win32/bin/arm-none-eabi-gcc.exe
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Users/Administrator/compiler/arm-gcc-win32/bin/arm-none-eabi-gcc.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Users/Administrator/compiler/arm-gcc-win32/bin/arm-none-eabi-g++.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- The ASM_MASM compiler identification is unknown
-- Found assembler: ml
-- Configuring done (22.8s)
-- Generating done (4.1s)
-- Build files have been written to: G:/Work/__HaloOS/haloosspace_new/output/rt_demo_E3650_DEV_KIT_gcc
[Compiler] compiler [gcc] and path is [].
[cmake_build] command is:  cmake --build G:/Work/__HaloOS/haloosspace_new/vcos/../output/rt_demo_E3650_DEV_KIT_gcc -j12 --clean-first
[  0%] Built target nuttx_context
[  0%] Built target apps_context
[  0%] Building C object apps/builtin/CMakeFiles/apps_builtin.dir/builtin_list.c.obj
[  0%] Building C object apps/builtin/CMakeFiles/apps_builtin.dir/exec_builtin.c.obj
[  0%] Linking C static library libapps_builtin.a
[  0%] Built target apps_builtin
[  0%] Generating linkscript.ld.tmp
[  0%] Built target ldscript_tmp
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/McalLib/src/Mcal_CacheAsm.S.obj
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/McalLib/src/Mcal_ArchOpt.S.obj
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/McalLib/src/Mcal_DelayAsm.S.obj
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/McalLib/src/memcpy_opt.S.obj
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/McalLib/src/memclr_opt.S.obj
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/lld/src/mram/Mram_IpAsm.S.obj
[  0%] Building ASM object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_asm.dir/platform/OsIf/src/OsIf_s.S.obj
[  0%] Linking ASM static library libmcal_asm.a
[  0%] Built target mcal_asm
[  0%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Dio_Cfg.c.obj
[  0%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Mcu_Cfg.c.obj
[  0%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Ea_Cfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Eep_PBCfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/McuExt_PBCfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Port_Cfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Uart_Cfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Lin_PBCfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Dma_PBCfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/Eth_PBCfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/boards/E3650_dev_kit/output/src/EthTrcv_PBCfg.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/configs/arch/armv8-r52/arm_irq.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eep/src/Eep_Irq.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eep/src/Eep.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Ea/src/Ea.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Ea/src/Ea_Crc16.c.obj
[  1%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Ea/src/Ea_Ops.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Dio/src/Dio_Ip.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Dio/src/Dio.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Lin/src/Lin_Ip.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Lin/src/Lin_Irq.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Lin/src/Lin_Uart.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Lin/src/Lin.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Ckgen.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_CkgenDrv.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Clk.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_ClkCfgNode.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_KickCore.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Pll.c.obj
[  2%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_PllDrv.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Reset.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_ResetDrv.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_ResetSig.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Rstgen.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Soc.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu_Xtal.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Mcu/src/Mcu.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Uart/src/Uart_Ip.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Uart/src/Uart_Irq.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Uart/src/Uart.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/McalLib/src/Mcal_Scr.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/McalLib/src/Mcal_Cache.c.obj
[  3%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/McalLib/src/Mcal_MemLibc.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/McalLib/src/Mcal_Delay.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/lld/src/mram/Mram_Ip.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/lld/src/Semag/Semag.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/McalLib/src/Mcal_Soc.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Port/src/Port_Ip.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Port/src/Port.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Rte/src/SchM_Base.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/OsIf/src/OsIf.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Dma/src/Dma_Ip.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Dma/src/Dma_Irq.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Dma/src/Dma.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eth/src/desc_op.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eth/src/dwmac_hw.c.obj
[  4%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eth/src/dwmac.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eth/src/Eth.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eth/src/EthBuff.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/Eth/src/EthDesc.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/EthTrcv/src/EthTrcv.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/EthTrcv/src/dp83848.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/EthTrcv/src/q21xx.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/EthTrcv/src/rtl820f.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/platform/EthTrcv/src/rtl9010x.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/vcos/eth_wrapper/EthIf.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/vcos/e3650_ea.c.obj
[  5%] Building C object arch/arm/src/exclude_chip/drivers/CMakeFiles/mcal_c.dir/vcos/e3650_board.c.obj
[  5%] Linking C static library libmcal_c.a
[  5%] Built target mcal_c
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_globals.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_initialize.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_register.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_unregister.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_loadmodule.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_unloadmodule.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_execmodule.c.obj
[  5%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_exec.c.obj
[  6%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_copyargv.c.obj
[  6%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_copyactions.c.obj
[  6%] Building C object binfmt/CMakeFiles/binfmt.dir/binfmt_dumpmodule.c.obj
[  6%] Building C object binfmt/CMakeFiles/binfmt.dir/builtin.c.obj
[  6%] Linking C static library libbinfmt.a
[  6%] Built target binfmt
[  6%] Building C object drivers/CMakeFiles/drivers.dir/loop/losetup.c.obj
[  6%] Building C object drivers/CMakeFiles/drivers.dir/misc/dev_null.c.obj
[  6%] Building C object drivers/CMakeFiles/drivers.dir/misc/dev_zero.c.obj
[  6%] Building C object drivers/CMakeFiles/drivers.dir/misc/ramdisk.c.obj
[  6%] Building C object drivers/CMakeFiles/drivers.dir/misc/mkrd.c.obj
[  6%] Building C object drivers/CMakeFiles/drivers.dir/note/note_driver.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/note/note_initialize.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/note/noteram_driver.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/note/note_handshake.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/note/notectl_driver.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/pipes/pipe.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/pipes/fifo.c.obj
[  7%] Building C object drivers/CMakeFiles/drivers.dir/pipes/pipe_common.c.obj
...
[  9%] Building C object arch/CMakeFiles/arch.dir/arm/src/armv8-r/cp15_cacheops.c.obj
[  9%] Building C object arch/CMakeFiles/arch.dir/arm/src/armv8-r/arm_dbgmonitor.c.obj
[  9%] Building ASM object arch/CMakeFiles/arch.dir/arm/src/armv8-r/arm_cpuhead.S.obj
[  9%] Building C object arch/CMakeFiles/arch.dir/arm/src/armv8-r/arm_cpuidlestack.c.obj
[  9%] Building C object arch/CMakeFiles/arch.dir/arm/src/armv8-r/arm_fpucmp.c.obj
[  9%] Building ASM object arch/CMakeFiles/arch.dir/arm/src/armv8-r/arm_fpuconfig.S.obj
[  9%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_boot.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_serial.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_allocateheap.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_timestamp.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_mpu_config.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_irq.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_ipicall.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_switchtask.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/e3650/e3650_syscall.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/common/arm_tcm.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/G_/Work/__HaloOS/haloosspace_new/vcos/vendor/semidrive/chips/common/arm_mpu.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_allocateheap.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_createstack.c.obj
[ 10%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_exit.c.obj
[ 11%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_getintstack.c.obj
[ 11%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_initialize.c.obj
[ 11%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_lowputs.c.obj
[ 11%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_modifyreg8.c.obj
[ 11%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_modifyreg16.c.obj
[ 11%] Building C object arch/CMakeFiles/arch.dir/arm/src/common/arm_modifyreg32.c.obj
...
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1832: Warning: setting incorrect section attributes for .rodata.os_task.CORE2_BSW_TASK_5MS_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1857: Warning: setting incorrect section attributes for .rodata.os_task.CORE2_INIT_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1882: Warning: setting incorrect section attributes for .rodata.os_task.CORE2_SHELL_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1907: Warning: setting incorrect section attributes for .rodata.os_task.CORE3_BSW_TASK_10MS_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1932: Warning: setting incorrect section attributes for .rodata.os_task.CORE3_BSW_TASK_1MS_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1957: Warning: setting incorrect section attributes for .rodata.os_task.CORE3_BSW_TASK_5MS_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:1982: Warning: setting incorrect section attributes for .rodata.os_task.CORE3_INIT_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:2007: Warning: setting incorrect section attributes for .rodata.os_task.CORE3_SHELL_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccz7c4rg.s:2032: Warning: setting incorrect section attributes for .rodata.os_task.DEFAULT_TCPIP_TASK_CFG
[ 99%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Os/isr_cfg.c.obj
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s: Assembler messages:
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:291: Warning: setting incorrect section attributes for .rodata.os_isr.Core0core0_eth_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:319: Warning: setting incorrect section attributes for .rodata.os_isr.Core0core0_ipicall_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:347: Warning: setting incorrect section attributes for .rodata.os_isr.Core0core0_systick_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:376: Warning: setting incorrect section attributes for .rodata.os_isr.Core0core0_uart_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:404: Warning: setting incorrect section attributes for .rodata.os_isr.Core1core1_ipicall_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:432: Warning: setting incorrect section attributes for .rodata.os_isr.Core1core1_systick_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:461: Warning: setting incorrect section attributes for .rodata.os_isr.Core1core1_uart_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:489: Warning: setting incorrect section attributes for .rodata.os_isr.Core2core2_ipicall_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:517: Warning: setting incorrect section attributes for .rodata.os_isr.Core2core2_systick_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:546: Warning: setting incorrect section attributes for .rodata.os_isr.Core2core2_uart_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:574: Warning: setting incorrect section attributes for .rodata.os_isr.Core3core3_ipicall_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:602: Warning: setting incorrect section attributes for .rodata.os_isr.Core3core3_systick_isr_ID
C:\Users\ADMINI~1\AppData\Local\Temp\ccd8wP0v.s:631: Warning: setting incorrect section attributes for .rodata.os_isr.Core3core3_uart_isr_ID
[ 99%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Rte/Rte.c.obj
[ 99%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Rte/Rte_SystemApplication_Core0.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Rte/Rte_SystemApplication_Core1.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Rte/Rte_SystemApplication_Core2.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Rte/Rte_SystemApplication_Core3.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/EthIf/ethif_lcfg.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/TcpIp/tcpip_cfg.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Os/application_cfg.c.obj
C:\Users\ADMINI~1\AppData\Local\Temp\cczgP8DC.s: Assembler messages:
C:\Users\ADMINI~1\AppData\Local\Temp\cczgP8DC.s:66: Warning: setting incorrect section attributes for .rodata.OsApplication.SystemApplication_Core0
C:\Users\ADMINI~1\AppData\Local\Temp\cczgP8DC.s:85: Warning: setting incorrect section attributes for .rodata.OsApplication.SystemApplication_Core1
C:\Users\ADMINI~1\AppData\Local\Temp\cczgP8DC.s:104: Warning: setting incorrect section attributes for .rodata.OsApplication.SystemApplication_Core2
C:\Users\ADMINI~1\AppData\Local\Temp\cczgP8DC.s:123: Warning: setting incorrect section attributes for .rodata.OsApplication.SystemApplication_Core3
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Os/counter_cfg.c.obj
C:\Users\ADMINI~1\AppData\Local\Temp\cc1IuZIW.s: Assembler messages:
C:\Users\ADMINI~1\AppData\Local\Temp\cc1IuZIW.s:72: Warning: setting incorrect section attributes for .rodata.os_counter.systemtimer0_cfg
C:\Users\ADMINI~1\AppData\Local\Temp\cc1IuZIW.s:91: Warning: setting incorrect section attributes for .rodata.os_counter.systemtimer1_cfg
C:\Users\ADMINI~1\AppData\Local\Temp\cc1IuZIW.s:110: Warning: setting incorrect section attributes for .rodata.os_counter.systemtimer2_cfg
C:\Users\ADMINI~1\AppData\Local\Temp\cc1IuZIW.s:129: Warning: setting incorrect section attributes for .rodata.os_counter.systemtimer3_cfg
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Os/spinlock_cfg.c.obj
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Os/schedtable_cfg.c.obj
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s: Assembler messages:
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:211: Warning: setting incorrect section attributes for .rodata.os_schdtbl.SCHEDTABLE_OSSCHEDULETABLE_CORE0_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:237: Warning: setting incorrect section attributes for .rodata.os_schdtbl.SCHEDTABLE_OSSCHEDULETABLE_CORE1_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:263: Warning: setting incorrect section attributes for .rodata.os_schdtbl.SCHEDTABLE_OSSCHEDULETABLE_CORE2_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:289: Warning: setting incorrect section attributes for .rodata.os_schdtbl.SCHEDTABLE_OSSCHEDULETABLE_CORE3_CFG
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:315: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_0_OsScheduleTable_Core0_EventList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:368: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_0_OsScheduleTable_Core1_EventList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:409: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_0_OsScheduleTable_Core2_EventList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:423: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_0_OsScheduleTable_Core3_EventList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:437: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_10_OsScheduleTable_Core0_EventList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:484: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_11_OsScheduleTable_Core0_EventList[]
...
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:2301: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_ExpiryPoint_9_OsScheduleTable_Core3_EventList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:2309: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_OsScheduleTable_Core0_ExpiryPointList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:3114: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_OsScheduleTable_Core1_ExpiryPointList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:3199: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_OsScheduleTable_Core2_ExpiryPointList[]
C:\Users\ADMINI~1\AppData\Local\Temp\ccM6YOAf.s:3284: Warning: setting incorrect section attributes for .rodata.os_schdtbl_exp_point.SchedTable_OsScheduleTable_Core3_ExpiryPointList[]
[100%] Building C object apps/vcos_examples/rt_demo/CMakeFiles/start_rt_framework.dir/platform_cfg/e3650_cfg/gen_data/Os/ipicall_cfg.c.obj
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s: Assembler messages:
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:144: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE0_IPICALL1
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:154: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE0_IPICALL2
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:164: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE0_IPICALL3
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:174: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE1_IPICALL0
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:184: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE1_IPICALL2
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:194: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE1_IPICALL3
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:204: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE2_IPICALL0
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:214: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE2_IPICALL1
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:224: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE2_IPICALL3
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:234: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE3_IPICALL0
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:244: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE3_IPICALL1
C:\Users\ADMINI~1\AppData\Local\Temp\ccannHYx.s:254: Warning: setting incorrect section attributes for .rodata.os_ipicall.OS_CORE3_IPICALL2
[100%] Linking C static library libstart_rt_framework.a
[100%] Built target start_rt_framework
[100%] Building C object CMakeFiles/nuttx.dir/empty.c.obj
[100%] Linking C executable nuttx
Memory region         Used Size  Region Size  %age Used
IRAM_FUNC:          0 GB       256 KB      0.00%
IRAM_NOC:        112 KB       128 KB     87.50%
IRAM_RW:      346416 B       624 KB     54.21%
CORE0TCMC:         64 KB        64 KB    100.00%
CORE1TCMC:         64 KB        64 KB    100.00%
CORE2TCMC:         64 KB        64 KB    100.00%
CORE3TCMC:         64 KB        64 KB    100.00%
IRAM_TEXT:      233024 B       412 KB     55.23%
IRAM_CONST:       99268 B       228 KB     42.52%
IRAM_DATA_INIT:        2592 B       128 KB      1.98%
IRAM_FUNC_INIT:          0 GB       256 KB      0.00%
IRAM_RESERVED:          0 GB         1 MB      0.00%
FLASH_TEXT:          0 GB       512 KB      0.00%
FLASH_CONST:          0 GB       128 KB      0.00%
FLASH_DATA_INIT:          0 GB       128 KB      0.00%
FLASH_FUNC_INIT:          0 GB       256 KB      0.00%
[100%] Built target nuttx
[100%] Generating nuttx.bin
[100%] Built target nuttx-bin
[100%] Built target nuttx_post
[100%] Generating nuttx.elf after nuttx build
Post-build step: Generating nuttx.elf
[100%] Built target nuttx_post_build
[100%] Built target post_build
# successful generate rt_demo.elf
Elapsed 306.19 s
End build with [rt_demo].
Elapsed 306.35 s
  ```


  > To compile `vbslite_demo`, replace `-app_name rt_demo` with `-app_name vbslite_demo` in the above command.

### 2.2 Compilation Instructions
For detailed explanations of compilation commands, refer to [HaloOS Compilation Framework Documentation](https://gitee.com/haloos/build/blob/master/README.md).

If you modify the code or add new code directories and update the `CMakeLists.txt` file, you need to delete the corresponding output directory and re-run the compilation command:
```bash
rm -r ./output  # Delete the output directory
python haloos_build.py -app_name rt_demo  # Recompile
```