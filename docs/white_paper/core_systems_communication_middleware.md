
### 3. Introduction to Core Systems  

#### 3.1 Communication Middleware  

##### 3.1.1 System Description  
The HaloOS Communication Bus (VBS, Vehicle Bus System) is a high-efficiency data interaction and communication platform specially built for the intelligent automotive field. Relying on standardized communication protocols, a modular architecture, and excellent real-time data transmission capabilities, this platform establishes a real-time and reliable information highway for the entire vehicle's electronic and electrical systems. With this platform, key services such as intelligent driving, power control, infotainment, and active safety can achieve seamless collaboration, providing a solid foundation for the efficient operation and functional expansion of intelligent vehicles.  

##### 3.1.2 Core Technical Features  

###### 3.1.2.1 Full-Domain Unified Deployment  
The new-generation electronic and electrical architecture poses two major technical challenges for in-vehicle communication middleware:  
- Intelligent driving systems require deterministic transmission of massive sensor data within milliseconds.  
- Vehicle control domain chips have limited computing power and storage space but need to deploy and manage hundreds of communication topics.  
Current industry communication middleware can only solve partial problems in limited domain scenarios, leading to fragmented communication protocols and high engineering management and maintenance costs during full-domain system deployment in vehicle scenarios. The HaloOS communication middleware achieves a customized DDS communication protocol based on vehicle scenarios, realizes lightweight design for MCUs, and builds a truly full-domain unified communication foundation, with core features as follows:  
- **VBS Pro Version**: Uses lock-free design and adaptive serialization/deserialization technologies to achieve zero-copy data transmission across processes and improve data transmission efficiency; effectively reduces invalid data transmission through sender-side message filtering and fixed-frequency message deduplication mechanisms.  
- **VBS Lite Version**: Relies on technical innovations such as custom communication protocols, intelligent merging of transmission channels, and logical communication endpoints to reduce system memory usage and meet the deployment needs of various resource-constrained MCU scenarios.  
- **Universal Feature**: Both VBS Pro and VBS Lite versions adopt a unified cross-domain data transmission protocol, eliminating the need for complex multi-protocol interactions in full-domain communication, simplifying communication processes, and enhancing overall system compatibility and usability.  

###### 3.1.2.2 Adaptive Multi-Transport Protocol  
In the automotive field, business function deployment is unordered, and underlying media protocols are diverse, including Ethernet, CAN, shared memory, and other media. In traditional solutions, a separate protocol stack must be customized for each transmission medium, and application programs must also adapt to different protocol stacks, which undoubtedly increases development complexity and costs significantly. To solve these problems, the HaloOS communication middleware has designed and implemented an adaptive multi-transport protocol solution, supporting business use of a unified interface layer, with the underlying layer adaptively matching transmission media such as Ethernet, CAN, and shared memory in different scenarios (e.g., cross-chip, inter-heterogeneous cores within a chip, and inter-process within a core), thereby effectively simplifying the development process.  

###### 3.1.2.3 Enhanced Reliability Mechanisms  
The HaloOS communication middleware not only supports basic transmission reliability guarantee mechanisms such as E2E verification, packet loss retransmission, in-order delivery, and network congestion control but also implements reliability enhancement solutions such as multi-path redundant transmission and shared memory exception transparent recovery to ensure that critical commands (e.g., those related to active safety) can be reliably delivered while achieving low transmission latency to adapt to strict vehicle-grade environments.  

###### 3.1.2.4 Multi-Level Security Protection  
The HaloOS communication middleware enhances security protection based on vehicle scenarios, implementing three levels of security protection as follows:  
- **Device Level**: Adopts a one-device-one-key PKI identity authentication mechanism to ensure that unauthorized devices cannot detect services provided by authorized devices, fundamentally preventing non-authorized devices from accessing the network and ensuring device-level security.  
- **Application Level**: Controls the permissions of communication entity applications, ensuring that only signed trusted applications can establish communication, effectively preventing untrusted applications from interfering with or stealing communication data and ensuring the security and reliability of the communication process.  
- **Data Level**: Uses session-level data encryption technology, so even if messages are intercepted by a man-in-the-middle, the original content cannot be obtained without a valid decryption key, comprehensively protecting the confidentiality of data during transmission.