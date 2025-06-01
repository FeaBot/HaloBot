
### 1. Overview&#xA;

#### 1.1 What is an Automotive Operating System?&#xA;

Against the backdrop of the AI-driven technological revolution profoundly reshaping the automotive industry, automotive operating systems are evolving into critical technical engines for hosting and driving vehicle AI intelligence. As highly complex software foundations integrating real-time performance, safety, and reliability requirements, they must effectively support the deployment and operation of various intelligent applications. Their fundamental task is to act as a key "central commander" and "resource scheduler" between the vehicle's complex hardware resources (including high-computing-power chips) and diverse upper-layer intelligent application software, providing a basic environment and operational guarantees for realizing various vehicle functions.


They need to abstract and manage underlying hardware "downward" with precision and efficiency, including but not limited to: unified driving and management of heterogeneous high-performance computing chips, various storage units, diversified perception sensor arrays, in-vehicle communication networks, and actuator systems critical to driving safety and control. This requires operating systems to provide deterministic real-time control capabilities, efficient resource virtualization and isolation mechanisms to organically integrate these physical hardware components, ensuring their collaborative, stable, and safe operation.


They need to support the evolving application ecosystem "upward" securely and flexibly, creating a secure, isolated, reliable, standardized, and easy-to-develop/deploy basic system environment for upper-layer application software—from intelligent vehicle control ensuring basic driving safety and comfort to intelligent driving systems safeguarding traffic safety and improving traffic efficiency. This requires operating systems to have good scalability, compatibility, and powerful middleware service capabilities.


Therefore, automotive operating systems serve as the foundation for vehicle connectivity and AI-driven intelligent transformation. The design of their architecture, technological advancement, and safety level not only directly determine the form and cost of the vehicle's electronic and electrical architecture but also profoundly influence the richness of functions, performance, and user experience.


#### 1.2 Development Trends of Automotive Operating Systems&#xA;

The evolution of automotive operating systems is closely tied to changes in automotive hardware architectures, jointly shaping the technological landscape of modern vehicles. Looking back, its development can be broadly divided into the following key stages:


**Stage 1: Mechanical Era (\~Before 1970s)**In this era, vehicles were primarily driven and controlled by mechanical components, with little to no involvement of electronic control units or software. Vehicle functions relied entirely on physical connections and mechanical linkages, making the concept of an operating system irrelevant.


**Stage 2: Electrification Era (1970s – Late 2010s/Early 2020s)**With the development of semiconductor technology and increasing requirements for vehicle functionality, safety, and comfort, electrification technologies began to be applied in automobiles. This stage can be further divided into:




*   **Function Stacking Phase (1970s – Early 2000s)**: Marked by the emergence of single-function controllers (ECUs), such as electronic fuel injection, anti-lock braking systems (ABS), and airbags being installed in vehicles. These early ECUs typically ran bare-metal programs or extremely simplified, manufacturer-specific real-time operating systems.


*   **Domain Centralization/Intelligentization Phase (Early 2000s – 2022)**: With the explosive growth of vehicle functions, the number of ECUs surged, driving the domain centralization of EE architectures, with operating systems in each domain developing independently:



    *   Vehicle Control Domain (e.g., powertrain, chassis, body): AUTOSAR CP (Classic Platform) gradually became the mainstream framework, providing standardized interfaces and components to standardize the development process of vehicle control software.


    *   Intelligent Driving Domain: Responsible for environmental perception, decision-making, planning, and execution control, characterized by data-intensive processing from multi-sensor fusion and computation-intensive tasks from AI algorithms. Therefore, operating systems need to support high-performance heterogeneous computing, often combining QNX, Linux, and AUTOSAR AP (Adaptive Platform).


**Stage 3: Spatial Robot Era (2022\~)**With the rapid development of artificial intelligence, particularly generative AI technologies such as large language models, penetrating the automotive field, computing power demands and software complexity in vehicles have grown exponentially. As a result, the hardware layer is evolving toward a central computing architecture, while the software layer is moving toward AI integration and domain-wide unification across the vehicle. This shift is driving a revolution in automotive operating systems:




*   **Transition from 'Smart' to 'Intelligent'**: With the deep integration of advanced AI technologies in the automotive field, automotive operating systems are undergoing a leap from "Smart" to "Intelligent." This transformation requires operating systems to have "Native for AI" characteristics—capable of intelligently scheduling and managing heterogeneous computing resources such as CPUs, GPGPUs, and NPUs to ensure high performance, determinism, and security; guaranteeing the reliable coexistence of functions with different safety levels and real-time requirements through isolation mechanisms; and providing standardized APIs and toolchains to support agile development and rapid iteration of upper-layer AI applications, making AI an endogenous driver for continuous vehicle evolution.


*   **Evolution Toward a 'Universal Spatial Intelligence Operating System'**: Intelligent driving functions require vehicles to operate safely, reliably, and in real time in the physical world, making them one of the earliest and largest-scale implementation scenarios for the spatial robotics concept. Operating systems capable of meeting such extremely complex scenarios have technical stacks with universality beyond intelligent vehicles themselves. Intelligent automotive operating systems have the potential to become "universal spatial intelligence operating systems" for future complex AI systems such as robots and embodied intelligent agents that require deep interaction with the physical world.