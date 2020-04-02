# Genetic-based-Load-Balancing-Cloud-Computing 
   Abstract— Job scheduling is a very significant aspect of cloud computing. Different kinds of services are provided to the consumers within desirable throughput. A lot of optimization techniques emerged to enhance efficiency and reduce expenses. This paper provides an approach to an online mode heuristic algorithm named as ‘Genetic Algorithm’ and its comparison with the batch mode heuristic algorithms. Cloudsim is used to perform the simulation. The results of the simulation show that the Genetic algorithm performs well compared to First Come First Serve Algorithm, Round Robin Algorithm, and Shortest Job First algorithm.
   
	                                                         Introduction
Cloud Computing is the on-demand delivery of computing resources such as servers, storage, databases, software, networking, analytics, and intelligence over the internet with a pay-per-use model. The users are charged based on their usage hence no additional payment for unused infrastructure. Various virtualization techniques are used for real-time information exchange [4]. 

There are a few most common Cloud deployments –

    Public Cloud - In Public cloud, the services are owned and operated by third-party service providers. These services are shared by multiple organizations. 

    Private Cloud – Private cloud refers to resources used by a single organization or business. Services such as servers, networks, and data centers are completely dedicated to one organization.

    Hybrid Cloud – This type of cloud combines the public and private cloud and allows the data to be shared among them. There are two approaches an organization can follow here – 
	Use the private cloud for some services and public cloud for others.
	Use the public cloud as a backup of the private cloud.

It provides three types of service models –

	Infrastructure as a Services (IaaS) - It provides services that include servers, networking, storage. It gives the highest extensibility and control over the management of computing resources. The flexible, innovative services are available on demand. It is similar to existing IT resources.

	Platform as a Services (PaaS) - It is a service to the user that gives a platform to develop or test the application on the cloud. It removes the need for organizations to manage the underlying infrastructure. It reduces the complexity of middleware as a service.

	Software as a Services (SaaS) - It is a method of delivering software applications over the internet on-demand and on a subscription basis. In this model, the user has not to think about how the service is maintained or how the underlying infrastructure is managed. The user should think only about how to use particular software. Everything else is managed and maintained by the service provider.

The demands of the cloud are increasing day-by-day. It has become difficult but necessary to provide the capability of handling the increasing requests. To maintain the efficacy of the performance, there should not be any difference in providing the services even after increasing the number of requirements [2]. 
         Job scheduling is the principal activity of cloud computing. Job scheduling with increasing needs has become the concern of cloud computing since it is very important to provide effective service. It mainly aims to distribute the system load and improve system performance. Achieving a high computing execution, managing efficiency amid jobs, the most desirable system throughput, and reduced expense is the intent of scheduling jobs. 

To achieve the goals stated above, it needs to allocate a specific job to a particular time and resource. There are two types of heuristic job scheduling algorithms in cloud computing which help provide optimization. Heuristic Algorithms find a solution among all possible options, although it does not guarantee that it is an optimal one – 

	Batch Mode Heuristic Scheduling Algorithm - The jobs are collected in a set and queued. The process of mapping of events begins in which jobs are mapped to a particular virtual machine at predefined time intervals.

	Online Mode Heuristic Scheduling Algorithm - In this mode, whenever a job comes, the job scheduler assigns it to an available machine.

On a cloud, the speed of each processor varies quickly as per the load available at that instance. It is more feasible to apply online mode scheduling algorithm. We are using an online mode heuristic scheduling algorithm called as ‘Genetic Algorithm’.

A genetic algorithm is a search heuristic algorithm inspired by Charles Darwin’s theory of natural evolution [5]. It reflects a process of natural selection where the fittest individuals are selected to produce offspring of the next generation. 

The process starts with the selection of fittest individuals from a population. They produce offspring which inherit the characteristics of parents. This offspring is added to the next generation. If parents have better fitness, then their offspring have a better chance of survival [10]. This process iterates until a generation with the fittest individuals is discovered [9]. We consider a set of solutions for a problem and select the set of best ones.

Initialization
The Genetic Algorithms require a population of n individuals to generate an optimal solution. Each individual is represented by a chromosome. From the n individual population, some individuals are selected based on some functions and operations are performed on them to find the fittest individual [3].

Fitness Function	
	This determines the productivity of individuals in the population. It represents the superiority and performance of one individual over the other. Low fitness value individuals are not selected for further operations. Fitness function is an important part of the Genetic Algorithm [3].
   
Selection
This is the process where the individuals are selected from the n individual’s population based on a strategy which can be tournament selection, roulette wheel, selection based on rank. This is an intermediate solution for the next generation.

Crossover
In this operation, two chromosomes are selected and divided into parts then they are combined in such a way that the first part of the first chromosome is combined with the latter part of the second chromosome and vice versa. This improves the searching mechanism in the Genetic algorithm [4].

Mutation
This operation is used after the crossover step. If the crossover is not able to generate the required diversity due to crossover between the same populations repeatedly and hence mutation operation is done to bring some variation in the population. Usually, the value of mutation is kept very low. This operation alters the gene value in the chromosome. This helps the Genetic Algorithm to produce even more optimal results [4].

	Simulation
Simulation is a demand for cloud computing to behold the implementation of real-time outlines [7]. There are various tools available for it such as Cloudsim, CloudAnalyst, iCanCloud, GroudSim, NetworkSim, SPECI, and Cloud Report. We are using Cloudsim and CloudAnalyst in our project.

	CloudSim
Cloudsim is a software which is used to perform modeling, simulation, and experiments in cloud computing services and infrastructures. "The tool is developed by Cloud Computing and Distributed Systems Laboratory at the University of Melbourne." We are using it to implement different job scheduling algorithms such as First Come First Serve algorithm, Round Robin algorithm, Shortest Job First algorithm, and Mainly Genetic algorithm. It can instantiate many data centers which consist of storage servers and physical host machines. These machines host multiple VMs executing several cloudlets. CloudSim can perform simulations of assigning and executing a workload on a cloud infrastructure [7].
 

	Problem Definition

	Suppose that there are m tasks T={t_1,t_2,,...,t_m}, and n virtual machines VM={〖vm〗_1,〖vm〗_2,...,〖vm〗_n}. It is a NP-complete problem which has n^m ways to allocate these tasks to VMs. When a task is bound to a virtual machine 〖vm〗_i the occupation time of 〖vm〗_j  depends on the length of task and the CU of the VM. The execution time for t_ij  on vmj is given by t_ij
                                       t_ij=L_i/C_j 
where  i∈{1,2,…,m}, 
j∈{1,2,…,n},
 L_(i )  represents the length of task t_i,
 and C_j  denotes the CU (Compute Unit) of virtual machine 〖vm〗_j.


Job Scheduling Objectives
	Designing a framework to implement the scheduling strategy and optimization algorithm for efficient task scheduling [1].
	Minimizes the makespan 
	Maximize throughput.
	Minimizes energy consumption.
	Minimize the idle time of the processor.
	Satisfies the quality of service.

	Proposed Method
The population is evaluated and selected to create a new generation by the fitness function. To find the correctness of the schedule the fitness function is used:

fitness(P)=min(U_1,U_2,…..,U_n)

where U_1,U_2,…..,U_n  are the chromosomes that represent the time taken to finish all the cloudlets execution for their respective assignment  [1][4].

	Algorithm
Step 1: Start
Step 2: Calculate the process priority as per their time
Step 3: Initialize the population as per the process priority 
Step 4: Evaluate the fitness function to determine the fitness    of each individual.
Step 5: Select the fittest chromosome.
Step 6: Perform crossover mapping over chromosomes.
Step 7: Perform mutation by changing the genes of individual parents.
Step 8: Add the chromosome to a new population
Step 9: Repeat steps 2 to 7 for all new arrival process
Step 10: Exit
      
What is a cloudlet?
        Cloudlet in Cloudsim defined the workload, which is to be executed during the simulation run of the cloudsim simulation engine. Cloudlet in Cloudsim is a model class that exists inside the package ‘org.cloudbus.cloudsim‘. Cloudlet is one of the most important models which defined the specifications for a simulation engine corresponding to the real-life candidate application to be considered for moving to a Cloud-based system.
        In contrast, we can also define this cloudlet as a single process or task being executed on the cloud-based system which is to be simulated through a Cloudsim simulation engine.

What is a Cloud Broker or Datacenter Broker?
	This class model a broker, which is responsible for mediating negotiations between SaaS and Cloud providers and such negotiations are driven by QoS requirements. The broker class acts on behalf of applications. Its prime role is to query the CIS to discover suitable resources/services and undertakes negotiations for the allocation of resources/services that can fulfill the application’s QoS needs. This class must be extended for evaluating and testing custom brokering policies.

Steps for Job Scheduling
	Create a container to store the VMs which can be passed to a broker later.
	Pass VM Parameters.
	Create a container to store the cloudlet.
	Pass cloudlet parameters.
	Create Data Centers.
	Create Broker.
	Create an Initial Population.
	Calculate the fitness index of the chromosome that is calculated by the time required for the completion of each task.
	Perform Crossover between the different chromosomes gene’s lists.
	Perform Mutations in the gene’s list.
	Calculate the fitness function and replace the old population by new population
	Repeat Step 9-11 until the stopping criteria condition is met.
	Take the chromosome that has the highest fitness index.
	Separate the final VM list and cloudlet list from the chromosome.
	Pass the list to the broker for simulation.
	Simulation will be finished after every cloudlet are assigned to VMs and finished their execution.

                                                            Results

       Makespan comparison of different algorithms
      Cloud Configuration	Specification	Makespan with GA	Makespan with SJF	Makespan with RR	Makespan with FCFS
      CC1	15 VMs, 40 Cloudlets	4.16	4.4	4.7	4.34
      CC2	25 VMs, 50 Cloudlets	3.19	3.76	3.58	3.72

The Genetic Algorithm achieves makespan equals to 4.16 seconds and 3.19 seconds for configuration CC1 and CC2 respectfully. Hence Genetic Algorithm was able to minimize the makespan compared to other algorithms like FCFS, SJF, and RR.
	
   
                                                             CONCLUSION
With the booming requests of cloud services today, there are issues of providing on-demand services and resources in a cloud environment and can’t be overlooked. Our work offers a persuasive of the time-saving method. The online heuristic job scheduling algorithm called as a Genetic Algorithm is conducted as experimental studies.
We tried to balance the workload by arranging VM based on their processing power and arranging the cloudlets according to their Length The list of VM and cloudlets is then submitted to the broker for the allocation. Broker allocates through a Genetic Algorithm and allocation of resources is done.
In this paper, we did a comparative analysis of the results of job scheduling algorithms like First Come First Serve algorithm, Round Robin Algorithm, Shortest Job First Algorithm. The results of using the genetic algorithm are load balancing, improved processor utilization, makespan minimization, cost minimization, and maximized throughput. The Genetic algorithm gives better results as compared to the batch heuristic algorithms. 


                                                                References


[1]	 C. K. Rath, P. Biswal and S. S. Suar, "Dynamic Task Scheduling with Load Balancing using Genetic Algorithm," 2018 International Conference on Information Technology (ICIT), Bhubaneswar, India, 2018, pp. 91-95.
[2]	M. Lagwal and N. Bhardwaj, "Load balancing in cloud computing using genetic algorithm," 2017 International Conference on Intelligent Computing and Control Systems (ICICCS), Madurai, 2017, pp. 560-565.
[3]	 Anshulika and L. A. Bewoor, "A genetic algorithm approach for solving a job shop scheduling problem," 2017 International Conference on Computer Communication and Informatics (ICCCI), Coimbatore, 2017, pp. 1-6.
[4]	H. A. Makasarwala and P. Hazari, "Using genetic algorithm for load balancing in cloud computing," 2016 8th International Conference on Electronics, Computers and Artificial Intelligence (ECAI), Ploiesti, 2016, pp. 1-6.
[5]	Genetic Algorithm chapter 2 and 3 shodhganga.
[6]	S. Yin, P. Ke and L. Tao, "An improved genetic algorithm for task scheduling in cloud computing," 2018 13th IEEE Conference on Industrial Electronics and Applications (ICIEA), Wuhan, 2018, pp. 526-530.
[7]	F. Fakhfakh, H. H. Kacem and A. H. Kacem, "Simulation tools for cloud computing: A survey and comparative study," 2017 IEEE/ACIS 16th International Conference on Computer and Information Science (ICIS), Wuhan, 2017, pp. 221-226. 
[8]	L. Zhao, Y. Dong and C. Huang, "A Study of Link Load Balancing Based on Improved Genetic Algorithm," 2013 Sixth International Symposium on Computational Intelligence and Design, Hangzhou, 2013, pp. 277-280.
[9]	Bhosale KK, Jadhav VD. A review of genetic algorithm for metal cutting processes and a research agenda. International Journal for Research in Applied Science & Engineering Technology (IJRASET). 2015;3(V).
[10]	Durairaj M, Kannan P. Improvised Genetic Approach for an Effective Resource Allocation in Cloud Infrastructure. International Journal of Computer Science and Information Technologies. 2015;6(4):4037-46.
[11]	S. S. Rajput and V. S. Kushwah, "A Genetic Based Improved Load Balanced Min-Min Task Scheduling Algorithm for Load Balancing in Cloud Computing," 2016 8th International Conference on Computational Intelligence and Communication Networks (CICN), Tehri, 2016, pp. 677-681.
