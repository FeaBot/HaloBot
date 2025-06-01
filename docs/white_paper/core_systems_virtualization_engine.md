
### 3.4 Virtualization Engine  

#### 3.4.1 System Description  
The HaloOS virtualization engine (LiVisor) serves as the virtualization foundation for building in-vehicle AI computing centers. It supports concurrent operation and collaboration of multi-domain services such as intelligent driving and vehicle control on centralized hardware platforms through resource pooling management and security isolation of CPU, memory, NPU, and I/O peripherals. Leveraging hardware characteristics, it adopts a hybrid software-hardware customized design to meet high-performance requirements for cold/hot starts, cross-domain communication, and high-speed peripheral access across different guest machines.  

#### 3.4.2 Core Technical Features  

##### 3.4.2.1 System-Level Security Isolation  
Traditional virtualization technologies are primarily designed for cloud scenarios, whereas in-vehicle services (Safety-Critical) require stricter isolation. LiVisor addresses this with static partitioning to ensure robust isolation of CPU, memory, interrupts, and exclusive peripherals:  
- **CPU Isolation**: Static binding of virtual CPUs (vCPUs) to physical CPUs (pCPUs) by physical CPU granularity prevents resource contention and ensures real-time performance.  
- **Memory Isolation**: A global static memory resource pool combined with CPU's Stage 2 MMU enables hardware-level isolation of virtual machine memory spaces, eliminating out-of-bounds access risks.  
- **Interrupt Isolation**: Virtualized system interrupt controllers partition interrupts and routing strategies by virtual machine, preventing cross-VM interrupt storms.  
- **Exclusive Peripheral Isolation**: Direct pass-through mode for exclusive devices via CPU's Stage 2 MMU and whitelist mechanisms ensures hardware-level I/O space isolation.  

##### 3.4.2.2 Efficient Resource Sharing  
For shared non-hardware-virtualized devices (e.g., UFS, Ethernet controllers) in in-vehicle domain convergence scenarios, traditional virtio paravirtualization incurs 30%-40% I/O performance loss. LiVisor's VM Exit-Less technology (based on virtio) restructures the vhost control plane to eliminate VM context switches (VM-Exit), reducing data transmission latency and enhancing device virtualization throughput.  

##### 3.4.2.3 High-Speed Cross-Domain Communication  
Traditional network-based virtualization communication suffers from high latency and bandwidth consumption. LiVisor uses shared memory for zero-copy communication between VMs, ensuring real-time performance for cross-VM interactions.  

##### 3.4.2.4 Reduced Performance Overhead  
Traditional virtualization faces challenges like high interrupt latency, frequent page faults, high TLB misses, and vCPU context switch overhead. LiVisor mitigates these with:  
- **vCPU Pinning**: Static 1:1 binding of vCPUs to pCPUs reduces context switch overhead.  
- **Large Page Pre-Mapping**: Pre-mapping virtual machine physical memory eliminates runtime page faults, reducing Stage 2 page tables and TLB misses for improved memory access performance.  
- **Interrupt Passthrough**:  
  - **Control Plane**: Guest OS interactions with vGIC are handled via the Hypervisor's vGIC module for security.  
  - **Data Plane**: Direct device interrupt delivery to target VMs bypasses the Hypervisor, ensuring performance.  

##### 3.4.2.5 Cold/Hot Start Acceleration  
LiVisor enhances user experience through:  
- **Customized VM-Level Parallel Boot**: Accelerates system startup.  
- **Fine-Grained VM-Level Hibernation/Wake-Up**: Ensures seamless transitions between operational states.  
- **Three-Tier Power Management**:  
  - **Peripheral-Level**: Dynamically suspends non-essential peripherals.  
  - **VM-Level**: Suspends entire VMs with associated CPUs and peripherals.  
  - **System-Level**: Powers down non-critical hardware/software resources in AON (Always-On) domains.