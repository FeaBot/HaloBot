# Deployment and Running Process  

## 1. Running on Development Boards  

### 1.1 SemiDrive E3650_DEV_KIT Development Board Flashing and Running  
- **Development Board**:  
  The `rt_demo` project provided by HaloOS supports running on SemiDrive E3650_DEV_KIT hardware. Developers who need to run debugging based on this board should purchase the [E3650_DEV_KIT development board](https://support.semidrive.com/product/detail/22) independently.  
- **Program Flashing Tools**:  
  E3650 supports multiple flashing tools (such as Jlink, Trace32, etc.). Developers need to select and prepare tools according to actual needs.  
- **Program Flashing**:  
  For program flashing methods, refer to [SemiDrive E3650_DEV_KIT Development Board Flashing Guide](https://gitee.com/haloos/vcos_vendor_semidrive/blob/master/docs/SemiDrive%20E3650_DEV_KIT%20%E5%BC%80%E5%8F%91%E6%9D%BF%E7%83%A7%E5%BD%95%E6%96%B9%E6%B3%95.md).  
  For program debugging methods, refer to [SemiDrive E3650_DEV_KIT Development Board Debugging Guide](https://gitee.com/haloos/vcos_vendor_semidrive/blob/master/docs/SemiDrive%20E3650_DEV_KIT%20%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E8%AF%95%E6%96%B9%E6%B3%95.md).  

### 1.2 Infineon A2G_TC397_5V_TFT Development Board Flashing and Running  
- **Development Board**:  
  The `rt_demo` project provided by HaloOS supports running on the Infineon KIT_A2G_TC397_5V_TFT development board. Developers who need to run debugging based on this board should purchase the [TC397 development board](https://www.infineon.com/cms/en/product/evaluation-boards/kit_a2g_tc397_5v_tft/) independently.  
- **Program Flashing Tools**:  
  TC397 program flashing supports multiple tools. This document only describes the [Aurix Flasher tool](https://softwaretools.infineon.com/tools/com.ifx.tb.tool.aurixflashersoftwaretool) provided by Infineon.  
  The Aurix Flasher tool supports program download via serial port or DAP/JTAG. For detailed flashing instructions, refer to the board’s User Manual, which can be downloaded from the TC397 development board link page.  
  If downloading programs via DAP or JTAG interfaces, purchase Infineon’s [miniwiggler tool](https://www.infineon.com/cms/en/product/evaluation-boards/kit_dap_miniwiggler_usb/).  
- **Program Flashing**:  
  For usage of the Aurix Flasher tool, refer to its help documentation.  
  Load the compiled ELF file from the `output` directory in the Aurix Flasher tool and execute "program". After flashing, disconnect and power off the board, then power it on again to run normally. At this point, connect to the board via serial port to view running logs and interact with Shell commands.  

## 2. Running on Simulator (No Hardware Required)  

### 2.1 Quick Run  
VCOS SIM (Simulator) allows simulation and debugging directly on the Ubuntu environment using configured Docker images without target hardware. Currently, the simulator can test many VCOS features, including scheduling tables, interrupts, Ethernet communication, etc.  

#### 2.1.1 Environment Preparation  
##### 2.1.1.1 Install linux-gnu-gcc Compiler  
> **Note**: VCOS SIM strongly depends on the linux-gnu-gcc compiler. Ubuntu usually comes with it pre-installed. If not, run the following command to install:  
```bash  
sudo apt update  
sudo apt install gcc  
```  
Verify the installation with `gcc --version`. A version number indicates successful installation.  

##### 2.1.1.2 Docker Environment Deployment  
Download the [vcos_sim Docker image](https://gitee.com/yanxiaoyong_1/sim-docker) and extract `vcos_sim.tar.7z.001` to get `vcos_sim.tar`.  
1. Import the Docker image tar package:  
   ```bash  
   docker load -i vcos_sim.tar  
   ```  
2. Start the vcos_sim Docker container (shared directory between Docker and Ubuntu for direct debugging):  
   ```bash  
   docker run -it --cap-add=NET_ADMIN --device=/dev/net/tun --name vcos_sim -v /home:/home vcos_sim /bin/bash &  
   ```  
3. Check if the container started successfully:  
   ```bash  
   docker ps -a  
   ```  
   The `vcos_sim` process should appear in the output.  
4. Enter the vcos_sim image:  
   ```bash  
   docker exec -it vcos_sim /bin/bash  
   ```  
5. After successfully starting the vcos_sim image, install the Docker and Dev Containers plugins in VS Code on the Linux system.  
6. Connect to the vcos_sim container via the installed plugins in VS Code to enable debugging in VS Code.  
![vscode连接vcos_sim](../_static/image/quick_start/vscode-connect-docker.png)  
7. Open the `haloosspace` folder in VS Code.  

#### 2.1.2 Compilation in Linux System  
The [Project Compilation](./02_compiling.md) section details how to complete compilation for running on development boards. To run `rt_demo` in the VCOS SIM virtual environment, switch to the `haloosspace/vcos/build` directory and execute the following command to generate the image file:  
```bash  
python vcos_build.py -app_name rt_demo -board_name E3650_DEV_KIT -compiler gcc -maketool ninja -sim 1 -all  
```  

#### 2.1.3 Running  
##### 2.1.3.1 Directly Run in vcos_sim Docker Environment  
```bash  
cd ./output/rt_demo_E3650_DEV_KIT_gcc_sim  
./rt_demo  
```  
The simulator currently integrates a virtual serial port module. If virtual serial ports exist on the host, the console uses them (open the virtual serial port `/dev/vttyM0` with a serial tool to interact with the simulator). If not, the console uses standard input/output (interact directly in the terminal).  
Two pairs of virtual serial ports (`/dev/vttyS0`/`/dev/vttyM0` and `/dev/vttyS1`/`/dev/vttyM1`) are created via `socat` in the Docker environment. The simulator binds to `/dev/vttyS0`, so use `/dev/vttyM0` for interaction.  

##### 2.1.3.2 Debug via GDB in VS Code  
1. Install the C/C++ plugin.  
2. Configure `launch.json` with the following example:  
    ```json  
    {  
        "version": "0.2.0",  
        "configurations": [  
            {  
                "name": "(gdb) 启动",  
                "type": "cppdbg",  
                "request": "launch",  
                "program": "${workspaceFolder}/output/rt_demo_E3650_DEV_KIT_gcc_sim/rt_demo",  
                "args": [],  
                "stopAtEntry": false,  
                "cwd": "${workspaceFolder}",  
                "environment": [],  
                "externalConsole": false,  
                "MIMode": "gdb",  
                "setupCommands": [  
                    {  
                        "description": "为 gdb 启用整齐打印",  
                        "text": "-enable-pretty-printing",  
                        "ignoreFailures": true  
                    },  
                    {  
                        "description": "Ignore SIGUSR1",  
                        "text": "handle SIGUSR1 nostop noprint pass",  
                        "ignoreFailures": true  
                    }  
                ]  
            },  
        ]  
    }  
    ```  
3. Start debugging directly via GDB in VS Code.  

#### 2.1.4 Exit  
When the simulator is running, the `nsh` prompt appears in the terminal or serial tool. Use the `poweroff` command to exit (recommended):  
```bash  
nsh> poweroff  
```  
If not exited via `poweroff`, residual processes may remain in the background. Force quit with:  
```bash  
pkill nuttx  
```