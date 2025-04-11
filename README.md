## Date: 09.04.25
### Title:  Delay- Aware Dynamic Resource Orchestration for IoT- Enabled Software- Defined Edge Networks

Note: 
1. I understand SDN and Mininet: https://youtu.be/DiChnu_PAzA?si=guJCo5Gabqr8Mw9z, https://en.wikipedia.org/wiki/Software-defined_networking
2. I understand OpenFlow protocol: https://youtu.be/l25Ukkmk6Sk?si=0KYSkMvDcsLanOTp

Summery:
In this paper authors proposed a novel framework to minimize delay in a IoT enabled SDN edge network. They proposed a framework name DRESIN which minimizes the delay. They experimented it on Mininet emulator. They laveraged evolutionany game theory to minimize the delay. 

**Handwritten note:** [Notes on Delay aware resource orchestration for IoT enabled SDN.pdf](Notes%20on%20Delay%20aware%20resource%20orchestration%20for%20IoT%20enabled%20SDN.pdf)


## Date: 10.04.24

### Title: From Technical Prerequisites to Improved Care: Distributed Edge AI for Tomographic Imaging

CBCT imaging: Cone Beam Computed Tomograph. It is used for scanning dental and facial xray. Create 3D image.
3-TECC Architecture: Three Tier Edge Cloud Continum. 
IoMT: Internet of Medical Things
FPGA: Field Programable Gate Array
IRS: Image Reconstruction System. It is basically a high-powered PC.

Summary: CBCT scan captures the 3D image. The image is either reconstructed at a local machine or in the cloud. It proposes a way to spread out the image processing algorithm from local to edge and cloud computing. 

Gap: No numeric data to back up the claim that this method improves processing and management. How much time does it reduce? What do you mean by improving data management? Does it make the data more organized? If they implemented it in a real-life scenario, how would the whole thing perform? The main issue is to reconstruct the image. Why do we need the edge AI?

- Here we are extending the image processing from local to the cloud. Do we even need this feature? Any hospital can afford a high computational PC. 700MB is it too large for the cloud?


### Title: Resource Slicing through Intelligent Orchestration of Energy-aware IoT Services in Edge-Cloud Continuum

Terminology section:
Network slicing in 5G: 
Nanoservice: 

Comments:
To forecast the energy requirement, you need energy to run the AI model. When using AI, does it reduce the overall energy consumption?
What is the difference between a nanoservice and a microservice? Is it only terminology?
The resource slicing idea is not clear. It does not mention the exact form of resource it manages (bandwidth, energy, time). 
The figure shows nanoservices being deployed in sensor-type devices. Can we do that? How do we install these apps on those devices? 


Summary: It just introduces the concept of resource slicing. The paper is very vague about types of resources it slices. No data to prove that resource slicing is a desirable feature.

### Title: Securing constrained IoT systems: A lightweight machine learning approach for anomaly detection and prevention. 
Summary: This is an anomaly detection paper. Used another person's dataset for memory usage and consumption. Trained a few models on the Edge Impulse website and then deployed them to Arduino and Raspberry Pi. Model deployed on IoT, edge, and cloud environment. 
Model used: naive bayes, decision tree, random forest, kNN

Comments: 
- No statistics about the data are provided.
- It claims to deploy the model on edge and cloud, but there is no mention of in which environment the model was deployed.


### Title: KPIs for Evaluating the Feasibility of Private 5G Networks in Hospitals
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
### Title: Weathering the reallocation storm: Large-Scale analysis of Edge Server Workload. 
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


### Title: Cloud and Edge Computation Offloading for Latency-Limited Services

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








































