## Date: 09.04.25
### Title:  Delay- Aware Dynamic Resource Orchestration for IoT- Enabled Software- Defined Edge Networks

Note: 
1. I understand SDN and Mininet: https://youtu.be/DiChnu_PAzA?si=guJCo5Gabqr8Mw9z, https://en.wikipedia.org/wiki/Software-defined_networking
2. I understand OpenFlow protocol: https://youtu.be/l25Ukkmk6Sk?si=0KYSkMvDcsLanOTp

Summery:
In this paper authors proposed a novel framework to minimize delay in a IoT enabled SDN edge network. They proposed a framework name DRESIN which minimizes the delay. They experimented it on Mininet emulator. They laveraged evolutionany game theory to minimize the delay. 

## Date: 10.04.24

### Title: From Technical Prerequisites to Improved Care: Distributed Edge AI for Tomographic Imaging

CBCT imaging: Cone Beam Computed Tomograph. It is used for scanning dental and facial xray. Create 3D image.
3-TECC Architecture: Three Tier Edge Cloud Continum. 
IoMT: Internet of Medical Things
FPGA: Field Programable Gate Array
IRS: Image Reconstruction System. It is basically a High Power PC.

Summary: CBCT scan capture 3D image. The image is either reconstructed at local mechine or in cloud. It propose a way to spread out the image processing algorithm from local to edge and cloud computing. 

Gap: No numeric data to bacup the claim that this method improve processing and management. How much time it reduces? What do You mean by improving data management? Does it make the data more organized? If they implemented it in a real life scenario how the whole thing performed? Main issue is to reconstruct the image, why do we need the edge AI for?

- Here we are extending the image processing from local to the cloud. Do we even need this feature? Any hospital can afford a high computational PC. 700MB is it too large that we need the cloud?


### Title:Resource Slicing through Intelligent Orchestration of Energy-aware IoT services in Edge-Cloud Continuum

Terminology section:
Network slicing in 5G: 
Nanoservice: 

Comments:
To forecast the energy requirement you need energy to run the AI model. When using AI, does it reduces the overall energy consumption?
What is the difference between a nanoservice and a microservise? Is it only terminology?
The resource slicing idea is not clear. It does not mention the exact form of resource it manages (bandwidth, energy, time). 
In the figure it shows nanoservices being deployed in sensor type devices. Can we do that? How do we install these apps in those devices? 


Summary: It just introduces the concept of resource slicing. The paper is very vegue about types of resources it slices, No data to prove that resource slicing is a desirable feature.

### Title: Securing a contrained IoT systems: a lightweight machine learning approach for anomaly detection and prevention. 
summary: This is an anomaly detection paper. Used other person's dataset for memory usage and consumption. Trained a few model on Edge Impulse website and then deployed it to arduino,raspberry pi. Model deployed on IoT, edge and cloud environment. 
Model used: naive bayes, decision tree, random forest, kNN

Comments: 
- No statistics about the data is provided.
- It claims to deploy the model on edge and cloud but there is no mention of in which environment the model was deployed.


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
### Title: 














































