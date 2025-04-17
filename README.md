## Date: 09.04.25
### 1.  Delay- Aware Dynamic Resource Orchestration for IoT- Enabled Software- Defined Edge Networks

Note: 
1. I understand SDN and Mininet: https://youtu.be/DiChnu_PAzA?si=guJCo5Gabqr8Mw9z, https://en.wikipedia.org/wiki/Software-defined_networking
2. I understand OpenFlow protocol: https://youtu.be/l25Ukkmk6Sk?si=0KYSkMvDcsLanOTp

Summery:
In this paper authors proposed a novel framework to minimize delay in a IoT enabled SDN edge network. They proposed a framework name DRESIN which minimizes the delay. They experimented it on Mininet emulator. They laveraged evolutionany game theory to minimize the delay. 

**Handwritten note:** [Notes on Delay aware resource orchestration for IoT enabled SDN.pdf](Notes%20on%20Delay%20aware%20resource%20orchestration%20for%20IoT%20enabled%20SDN.pdf)


## Date: 10.04.24

### 2. From Technical Prerequisites to Improved Care: Distributed Edge AI for Tomographic Imaging

CBCT imaging: Cone Beam Computed Tomograph. It is used for scanning dental and facial xray. Create 3D image.
3-TECC Architecture: Three Tier Edge Cloud Continum. 
IoMT: Internet of Medical Things
FPGA: Field Programable Gate Array
IRS: Image Reconstruction System. It is basically a high-powered PC.

Summary: CBCT scan captures the 3D image. The image is either reconstructed at a local machine or in the cloud. It proposes a way to spread out the image processing algorithm from local to edge and cloud computing. 

Gap: No numeric data to back up the claim that this method improves processing and management. How much time does it reduce? What do you mean by improving data management? Does it make the data more organized? If they implemented it in a real-life scenario, how would the whole thing perform? The main issue is to reconstruct the image. Why do we need the edge AI?

- Here we are extending the image processing from local to the cloud. Do we even need this feature? Any hospital can afford a high computational PC. 700MB is it too large for the cloud?


### 3. Resource Slicing through Intelligent Orchestration of Energy-aware IoT Services in Edge-Cloud Continuum

Terminology section:
Network slicing in 5G: 
Nanoservice: 

Comments:
To forecast the energy requirement, you need energy to run the AI model. When using AI, does it reduce the overall energy consumption?
What is the difference between a nanoservice and a microservice? Is it only terminology?
The resource-slicing idea is not clear. It does not mention the exact form of resource it manages (bandwidth, energy, time). 
The figure shows nanoservices being deployed in sensor-type devices. Can we do that? How do we install these apps on those devices? 


Summary: It just introduces the concept of resource slicing. The paper is very vague about types of resources it slices. No data to prove that resource slicing is a desirable feature.

### 4. Securing constrained IoT systems: A lightweight machine learning approach for anomaly detection and prevention. 
Summary: This is an anomaly detection paper. Used another person's dataset for memory usage and consumption. Trained a few models on the Edge Impulse website and then deployed them to Arduino and Raspberry Pi. Model deployed on IoT, edge, and cloud environment. 
Model used: naive bayes, decision tree, random forest, kNN

Comments: 
- No statistics about the data are provided.
- It claims to deploy the model on edge and cloud, but there is no mention of in which environment the model was deployed.


### 5. KPIs for Evaluating the Feasibility of Private 5G Networks in Hospitals
**Note**:
- Private 5G network: The main idea is that each institution or use case will have its dedicated network, which will be connected to the external big network. 
- iperf client and server model: iperf is an open-source network testing tool that measures the performance of a network link.
- AR/VR traffic: AR (Augmented Reality) and VR (Virtual Reality) traffic refers to the digital data transmitted over a network to support applications that overlay digital information on the real world (AR) or immerse the user in a fully virtual environment (VR). AR and especially VR applications often require the transmission of high-definition video streams, 3D graphics, and sensor data in real time. For VR, this can mean streaming two separate high-resolution video feeds (one for each eye), all while maintaining high frame rates.
- For security testing, the author tested DoS using Low Orbit Ion Cannon (LOIC), UDP flood, and Nmap tool to scan idle ports in Raspberry Pi.
- The author did not define any KPI (Key Performance Indicator); instead, he measured values of different aspects of the network. 

**Summary**:
In this paper, the author performed many tests and measurements on a private 5G network of a hospital. The tests include a  connectivity test, a bandwidth test, a stability test, a scalability test, a performance test, a resilience test, a video quality test, and a security test. 

**Comments**: 
- Test bed architecture is not clear. The backbone network is not understandable.
- In the connectivity test, the author tested the latency in ms using the ping command. This latency depends on the location of the server we are pinging. What server and what distance are we covering here?
- Why is the average ping response time 103ms during the network bandwidth test?
- In the scaleability section, the average jitter time is 5.58 ms for 10 connections. Is it acceptable?
- There are multiple times when the author claimed that his experimental value is within the acceptable range, but he failed to mention the acceptable value.
- What does it mean to run the video on a network?

## Date: 11.04.25
### 6. Weathering the reallocation storm: Large-Scale analysis of Edge Server Workload. 
**Note:**
- Superfluous: extra, redundant, surplus, excess. 
- This paper studied load balancing/ workload balancing on edge servers.
- Grid computing:
- The author identified a phenomenon named reallocation storm, where reallocation triggers new reallocation.
- A cloud uses three reallocation strategies.
  - Proximity strategy: reallocate workload to the nearest ES (Edge Server).
  - Bottom-up strategy: You have to do the bookkeeping for all the ESs in the network so that you can assign the workload to a server that has the lowest workload. This method can not minimize the latency.
  - Random strategy: Randomly reallocating an ES.
 
- Reallocation storm: Suppose there is a number of ES in a network. All of these ES have reached nearly to their capacity. In this situation, if there is any reallocation, there will be a butterfly effect. This is called the reallocation storm.
- Vertical workload: Traffic coming from access point to the ES. The access point could be a router or a base station.
- Horizontal workload: Traffic that is coming from the another adjacent ES. 

**Summary:**
The author identified a phenomenon called reallocation storm. He used the Wi-Fi data of panoulu, which covers the oulu city region and employs 20 ES. When all the servers are running nearly at full capacity, then the vertical connections are reallocated. During this time, horizontal connection/workload is refused. Edge server uses the cloud computing's workload management strategy. The author argues that these strategies are not good enough for the edge servers. He suggested that we should look for a new kind of strategy. He proposed that we can avoid reallocation by preemptively triggering reallocation. 

**Research Direction:** We can develop a new strategy and test it on the edge.

**Comment:**
- They have a dataset that contains wifi network data of 47M connections with over 800 access points. How did the author find the phenomenon from the dataset?
- Network topology is not available in the paper.
- Statistics about the dataset are not enough.
- The author divided the dataset into 80% for training and 20% for testing. However, he does not mention using any AI/ML model.
- No description of simulation set up.
- It seems the author just analyzed the dataset.
- Why the author took different average time is not clear to me. 


### 7. Cloud and Edge Computation Offloading for Latency-Limited Services

**Notes:**
- MEC: Multi-access Edge Computing.
- NP-heard:
- The author developed an algorithm for offloading tasks from the edge server to the cloud server. The algorithm was simulated and compared with the baseline and optimal solution. 

**Summary:**
The main idea is to develop and test the resource allocation algorithm. [*A revisit is required to understand what the algorithm does.*] 
**Comments:**
- MEC will be part of the 5G network.
- No mention of the baseline algorithm.
- The algorithm is well defined and notation heavy. I didn't inspect the algorithm. I needed some time to examine the algorithm.
- Topology is well defined. 

## Date: 12.04.25
### 8. SDN Enhanced Resource Orchestration of Containerized Edge Applications for Industrial IoT

**Note:**
- A MEC (Multi Access Edge Computing) contains programs that automate resource allocation. These programs could be called Agents.
- SDN switch:
- SDN controller:
- Edge Server:
- OpenDaylight:
- PowerAPI:
- HWPC:
- RAPL
- GO
- FFmpeg:
- Mininet

**Summary:**
When a UE moves from one MEC to another MEC, docker will replicate or migrate the MEC application to the new MEC application. In this paper, the author measured the amount of delay it introduces and the power consumption for such a task. 
**Research Idea:** 
We can record the speed of the UE. If it is a standstill, we don't need to migrate the application from one MEC to another. But if the UE is on the run, based on its speed, we can migrate the app to the next two or three MEC so that when the UE handover happens, the UE can get the service without any delay. 

**Comments:**
- Docker and Kubernetes take a significant amount of space on a hard disk. Is it a good idea to put them on the edge server?
- The abstract and the conclusion are not well written. I did not understand what problem the author was addressing.
- In the introduction section, it mentions the requirement of software processes being migrated between MECs. Is it possible because each process has its own state? If it is stopped, then it will lose all the processed data/state.
- It mentions offloading tasks to a UE. Is it possible? UE has little processing capability.
- The introduction section doesn't introduce the problem.
- Testbed setup is not clear. It is not clear how data passes from one node to another. The mechanism for the handover and docker app migration decision-making process is not clear. 

### 9. Edge computing server placement with capacitated location allocation.
**Note:**
- The PanOulu Wifi dataset needs to be inspected.
- Github R based code link: [Github Ripo](https://github.com/terolahderanta/rpack)

**Summary:** 
The author has developed a novel algorithm called PACK. It takes into account parameters such as workload, computing capacity, performance metrics, latency, number of edge servers, co-location server and APs, workload allocation, location preference, and reliability. It provides an optimized location to place the edge server as well as an optimal method to allocate other resources to minimize the latency within the acceptable range. 

**Idea:**
- Instead of using historical data, can we take the population data of that particular area into account? Can we calculate population variation/flux to predict how many resources we need at a time in a worst-case scenario?
- Can we deploy a central edge server to facilitate the computational offloading instead of distributing the load among other co-servers?

**Comments:**
- No statistics about the dataset. No link to the dataset.

## Date: 13.04.25
### 10. SDN-enabled resource orchestration for industrial IoT in collaborative edge cloud networks.
**Notes:**
- Service level agreement:
- Constrained satisfaction problem:
- ROI: 
- Savile Row:
- Essence prime:
- HVAC: Heating, Ventilation, and air conditioning. 
- NP hard optimization problems are solved using prime essense language.
- CloudSimDN and PureEdgeSim are simulation software
- The solver takes 0.47 to 0.5 ms to solve the constrained problem.
- The resource orchestration improves 4% task success.

**Summary:**
The author made a topology in a simulation software and then tested his ideas. This paper proposes a resource allocation method in two steps. In the first step, you have to identify the number of edge servers you would like to deploy, what kind of application you would run on the network, etc. You have to formulate a constrained optimization problem. After solving it using the solver (Essense Prime language), SDN will assign the resources to each edge server. In this way, resource utilization will be efficient. 

**Comments:**
- IoT has a heterogenous nature, but I don't think it is unpredictable.

### 11. Reinforcement Learning based cloud and edge resource allocation for real-time telemedicine.
**Notes:**
- Q-learning:
- Reinforecemnt learning:

**Summary:**
The author trained a Q-learning reinforcement learning algorithm for resource allocation. He showed that using this method improves drop rates. It is not mentioned whether it decreases the latency. 

**Comments**
- In the introduction, instead of introducing the problem, the author talked about kind of related work. A graph war is required to better understand the scenario in which the author is trying to work.
- Just developed a reinforcement learning algorithm in a simulation and then tested it.
- How the author connected the algorithm with the resource allocation simulation is not clear.
- How much time does the algorithm take to predict the next MEC?
- It says the model interacts with the system. It is not clear to me how exactly it interacts with the system. There are no model parameters mentioned. 

**Idea:**

### 12. Securing edge services for future smart healthcare and industrial IoT application
**Notes:**
- The idea of the 'Naked World' or Nearable device is new to me.

**Summary:**
The author envisioned a healthcare system where a person would go for a checkup. He would be able to access the machines using his biometric identity. To enable this, he proposed to use three key technologies: IoT, edge, and blockchain technology. In his thesis, he worked on three aspects of the futueristic hospital, such as biometric system, mechanism to add node to the systems, and blockchain + edge computing for ensuring low latency and trust on the system. 

**Comments:**
- It is a very good paper. It provides network topology and simply describes the main ideas.
- It is just a description of the whole thesis work. 

**Idea:**

## Date: 14.04.25

### 13. Resource-aware orchestration of IoT application in edge cloud continuum with 6G  
**Note:**
- 6G architecture:
  
**Summary:**
This is not a real research paper. It is more like a proposal for future work.
- The author wants to deploy IoT apps in a way that fulfills some system requirements. These system requirements include CPU, GPU, RAM, Disk, energy efficiency, low latency, and high bandwidth. This research will be carried out in simulation software, for example, PureEdgeSim, CloudSim, iFogSim, etc.

### 14. AI-driven data management on distributed computing for digital healthcare.
**Notes:**
- Reinforcement learning:
- Federated learning:
- I need to interact with the simulation software to better understand how these research works are carried out using them. 

**Summary:**
This is a proposal-type paper. It focuses on data management and distributed computing. For the data management, the author wants to create a distributed system to host the data. This data could be various types. After hosting the data on resource-constrained nodes, the  author wants to leverage that data to train a federated learning AI. In federated learning, a model is distributed on different nodes. Each node sees a part of the data, and it is trained using those data. After the training period, the learning is aggregated to a global model.  

**Comments:**
- I know the concepts of reinforcement learning and federated learning, but I haven't used them. I need to try them first. 

**Idea:**

### 15. Energy profiling and analysis of 5G private networks: evaluating energy consumption patterns.
**Notes:**
The OAI Box contains two things - CN5G and gNB
- USRP B210: It is a radio unit of gNB
- Netio PowerBox 4KF: Software to measure energy. 

**Summary:**
Energy profiling is important to understand how a network consumes energy. This data helps us to optimize the energy cost. In this paper, the author showed an experimental setup and recorded network energy consumption patterns at various points. 

**Comments:**
- Good diagram of the experimental setup. It would be better if the author described the data communication between the nodes.
- 

**Idea:**

### 16. Semantic slicing across the distributed intelligent 6G wireless network.
**Notes:**
- Cyber-physical device:
- Data slicing: It is like filtering the data before sending it anywhere. The filtering could be based on time frame, location, or any other criteria.
- AI model slicing: This is equivalent to federated learning, which means a model will be split into multiple nodes, and each part of the model will be trained based on local data. After that, the knowledge will be shared with the global system.
- Network slicing: It is a core concept of 5G. Network slicing means customizing or reconfiguring a network system for a particular use case. For example, a hospital has a different requirement than a university 5G system. So, the network resources, such as bandwidth, QoS, latency, and services, will be customized for each case.
- Resource access slicing: Dynamically allocating and managing access to multiple resources within a network. 
- Sensor slicing: Suppose there is a traffic camera. This traffic camera captures many important information. Police, municipalities, and road construction engineers can all get the data from the same camera without the need to install another camera. All of them will get the data they need without interfering with others' data acquisition. This is called sensor slicing. 

**Summary:**
Semantic means meaning. So, semantic slicing means dividing something based on some meaning. In this paper, the slicing starts from the sensors and propagates to the cloud level. The idea is that some AI model will first analyze the data and then keep only the necessary data. This way, the bandwidth usage will be efficient. We don't need to send all the data to the cloud. As we are using AI and based on the analysis, we are only keeping the data that is important; this is called meaningful acquisition of data, or semantic slicing. However, this concept is not only limited to data slicing. You can refer to the note section, where I mentioned other slicing concepts. 

**Comments**
- This paper only introduces the concept called 'semantic slicing'
- There is no concrete data or analysis about whether this slicing is good or bad.

**Research questions:**
- Are there any quantitative analyses of this method? If not, we can try. 

## Date: 15.04.25
### 17. Distributed network and service architecture for future digital healthcare.
**Notes:**
- Serverless edge computing model
- Docker swarm, Kubernetes
- FaaS: Functions As A service
- FaaS: It is a small logical units that become alive wen needed. They are of small sizes and usually runs for a short period of time. It does not require a dedicated server. It enables serverless computing.
- Nanoservices: The processing task is split into smaller pieces and deployed to IoT devices in an efficient manner this is called nanoservice.
- Latency could be of two types: 1. Computation latency 2. communication latency

**Summary:**
This paper is the summary of four papers of this group. The author proposed a three tier edge architecture which extented the cloud computing near to the user. It adds two additional hops for data processing. One hop is the edge server, another hop is the local edge device. When we are bringing computation to the local level we will encounter many issues and question. First question would be what computation should we do where? This problem is solved by dividing the whole task into three smaller part based on the computational capacity of each layer. For example the raspberry Pi could filter out the sensor data. MEC could aggregate the data and provide realtime feedback such as if the patient having any heart attack right now. Then the cloud could be used for storing the data and maybe we can perform annual analysis of health data from there. The Raspberry Pi is very important. Instead of just installing one fixed application to it, we can do it dinamically. For example a scenario may arise such that we need to add an extra sensor to a patient. In that case we need to collect the data from the patient and perform a light weight filtering. As the sensor could provide different kind of data, we need different application to handle that. This new apps could be dinamically installed to it by MEC. Let's say all of these works. Now we need to ensure security. For this purpose the author propose to use blockchain. Virtualization and blockchain introduces some dealy/latency. However author said it is feasible to develop such a three tier system. 

**Comments:**
- How optimal values are defined?
- When orchestraing application or images we need to store all the images somewhere, we need to load/install them somewhere how do we do that?
- To install docker images to a device we need a docker first. Docker uses a lot of space. Can we install it on Raspberry Pi? If not, how orchestration install these application?
- Where is the blockchain installed and what it does? How does it do it? What is its input? What is its output?

**Idea:**

## Date: 17.04.25 
### Keyword: Microservice orchestration, distributed microservice architecture, nanoservice architecture, resource-aware microservice orchestrator. E-Ware, Tomohead. Related paper, project, demos.
### 18. Title: Microservice Orchestration for Process Control in Industry 4.0 
**Notes**
- The author used the Molecular framework from JavaScript to develop the microservices.
- There are two types of orchestration: 1. Orchestration (Central master service works along with slave services. All communication passes through the Transporter) and 2. Choreograph (It is like a ring topology. One server passes the task/information to the next one)

**Summary**:
In this paper author created four microservices and isntalled them in two Raspberry Pi to control a industrial processing mechine. The mechine has pump and water vulbs. Microservices collects information from the sensors connected to the vulbs and send to the Raspberry Pi. 

**Comments**:
- It is a static installation system. It doesn't dynamically deploy the service.
- This is a good use case-based analysis. 


### 19. Title: Beethoven: An Event-Driven Lightweight Platform for Microservice Orchestration
**Summary**: This paper proposes a platform called Beethoven for rochestration. When orchestrating microservice there are challenges related to scaling and communication between each microservices. 

















































