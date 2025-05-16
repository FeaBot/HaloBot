# Project Compilation

## 1. Prepare the Compilation Environment

### 1.1 Install Dependent Plugins for VCOS Studio Configuration Tool

#### 1.1.1 Windows System
1. Open PowerShell with **Administrator privileges** and navigate to the root directory `haloosspace`.
2. Execute the following command:
    ```bash
    python ./vcos/vcos_studio/configurator/init_env.py -a
    ```

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

  > To compile `vbslite_demo`, replace `-app_name rt_demo` with `-app_name vbslite_demo` in the above command.

### 2.2 Compilation Instructions
For detailed explanations of compilation commands, refer to [HaloOS Compilation Framework Documentation](https://gitee.com/haloos/build/blob/master/README.md).

If you modify the code or add new code directories and update the `CMakeLists.txt` file, you need to delete the corresponding output directory and re-run the compilation command:
```bash
rm -r ./output  # Delete the output directory
python haloos_build.py -app_name rt_demo  # Recompile
```