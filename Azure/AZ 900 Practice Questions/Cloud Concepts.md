# Microsoft Azure AZ900 - Describe Cloud Concepts

## Paper 1

1. ### Private clouds

- Private clouds provide greater control for the company and its IT department compared to public clouds. This increased control allows for more customized security, compliance, and performance configurations, catering to the specific needs of the organization.

2. ### Benefits of Public Cloud Computing

- On-demand capacity: Public cloud computing allows businesses to scale their resources up or down based on demand, providing flexibility and efficiency.

- Globally scalable: Public cloud providers offer infrastructure that is globally distributed, enabling businesses to deploy applications and services close to their users around the world, improving performance and reliability.

3. ### Cloud Attribute: Reliability

- Reliability is the cloud attribute defined by knowing your application will perform as expected regardless of customer demand. Reliability ensures that the cloud infrastructure can handle varying levels of workload without affecting the performance or availability of applications.

4. ### Governance in the Cloud

- Governance in the cloud ensures that standardized environments are created and enforced to meet corporate or government requirements. This attribute is crucial for maintaining compliance, security, and operational consistency across cloud deployments.

5. ### Characteristics of Public Clouds Compared to Private Clouds

- Higher scalability: Public clouds offer greater scalability due to the vast infrastructure managed by cloud providers. Resources can be easily scaled up or down based on demand, providing flexibility and efficiency.

- Lower costs: Public clouds typically have lower costs because the infrastructure and maintenance expenses are shared among many users, leading to economies of scale. Users pay for what they use, avoiding the large capital expenditures associated with private clouds.

6. ### IaaS (Infrastructure as a Service)

- Amongst IaaS, SaaS, PaaS, FaaS; IaaS provides the most flexibility and control because it allows you to rent IT infrastructure (servers, virtual machines, storage, networks, and operating systems) on a pay-as-you-go basis. This model gives you full control over the hardware and software configuration, enabling you to customize and manage the environment according to your specific needs.

7. ### Predictability in the Cloud

- Predictability involves understanding and forecasting the costs associated with cloud resources. It allows organizations to plan and budget effectively by analyzing current usage trends to anticipate future expenses. This attribute is essential for financial planning and ensuring cost efficiency in cloud operations.

8. ### Vertical Scaling in Azure Compute

- Vertical scaling involves increasing the compute capacity of an existing resource, typically by adding more CPUs or RAM to an existing virtual machine. This process usually requires downtime because the VM needs to be resized, which often involves stopping and restarting it.

9. ### Manageability in the Cloud

- Manageability involves the ability to effectively oversee, configure, monitor, and interact with cloud resources. It encompasses tools and processes that facilitate the management of cloud infrastructure, ensuring that resources are used efficiently and effectively, and that the system is maintained properly. This attribute is crucial for maintaining operational efficiency and achieving business goals through the cloud.

10. ### Platform-as-a-Service (PaaS)

- PaaS (Platform as a Service): Provides a platform allowing customers to develop, run, and manage applications without worrying about the underlying infrastructure. Example: Azure App Service, AWS Elastic Beanstalk, Azure SQL Database, Google app engine.

- SaaS (Software as a Service): Delivers software applications over the internet on a subscription basis. Users access the software via a web browser, and the provider manages all aspects of the application. Example: Microsoft Office 365.

- PaaS solutions, like Azure SQL Database, provide managed database services where the underlying infrastructure, including operating system patches, backups, and high availability, is managed by Azure. This allows you to focus on database management and application development rather than maintaining the infrastructure. An Azure SQL instance is considered a PaaS service because you do not manage any guest servers as with IaaS.


## Paper 2

11. ### Hybrid Cloud Solution

- If your company periodically needs additional compute capacity beyond what your datacenter can support and aims to minimize costs and administrative effort, you should implement a hybrid cloud solution.

12. ### Azure Functions

- An example of serverless cloud computing within Azure is Azure Functions.

- Other examples include Azure Logic Apps, Azure Event Grid, Azure Container Instances and Azure Cosmos DB Serverless

- While Azure App Service generally involves provisioning of resources, its integration with Azure Functions can provide a serverless experience for web apps, APIs, and mobile backends, allowing you to build and deploy applications without managing infrastructure.

13. ### VM Reliability

- If you need to ensure reliable operation of your VM-hosted application in case of a datacenter outage, you should deploy additional virtual machines to host the application in another zone. This strategy ensures high availability by distributing your application across multiple availability zones within the same Azure region, providing fault tolerance and resilience against datacenter failures.

14. ### Active Directory Domain Controllers

- Active Directory domain controllers are servers in a Windows network that manage user access and security. They handle login requests, store information about users and computers, and ensure that all directory information is consistent across the network.

15. ### Infrastructure as a Service (IaaS)

- If you are deploying virtual machines into Azure with the intent of using them as Active Directory domain controllers, this setup is considered Infrastructure as a Service (IaaS). IaaS provides virtualized computing resources over the internet, allowing you to create and manage virtual machines and other infrastructure components without worrying about the physical hardware.

16. ### Software as a Service (SaaS)

- If you are migrating your on-premises Microsoft Exchange email system to Microsoft 365, this is considered Software as a Service (SaaS). SaaS provides fully managed software applications over the internet, where the service provider handles all aspects of the application, including infrastructure, maintenance, and security.

17. ### Platform as a Service (PaaS)

- If you are migrating a web-based application built on the Python Flask framework to Microsoft Azure and want a solution that requires minimal ongoing maintenance, you should recommend Platform as a Service (PaaS). PaaS solutions provide a managed environment where you can deploy, run, and scale your applications without worrying about the underlying infrastructure.

- Software is the wrong for this because it delivers fully developed applications that are ready to use, rather than providing a platform for deploying and managing custom web applications like the Python Flask web app you are migrating.

18. ### Manageability in the Cloud

- Manageability in the cloud refers to _how you interact with and implement different cloud-based resources_. 

19. ### Platform as a Service (PaaS)

- If you want to build and host your website on Azure without managing the underlying infrastructure, you should choose Platform as a Service (PaaS).

20. ### Security in the Cloud

- The cloud attribute of security is described as having full control, or even choosing how much control you want, over your cloud resources' security configuration. 

21. ### Governance in the Cloud

- The cloud attribute of governance is described as the ability to create and enforce standardized environments, usually to meet corporate or government requirements.

22. ### Scalability in Cloud Computing

- The concept of "scalability" is defined as the ability of a system to handle increased load. This means that a cloud service or infrastructure can efficiently scale up (handle more workload) or scale down (reduce resources) based on demand, ensuring performance and availability without manual intervention.

## Paper 3

23. ### Role-Based Access Control (RBAC)

- Role-Based Access Control (RBAC) is an authorization system built on Azure Resource Manager that provides fine-grained access management of Azure resources. It allows you to assign roles to users, groups, and service principals, enabling you to control who has access to specific resources and what actions they can perform.

24. ### Resource Groups

- The logical container used to group together and manage resources with the same lifecycle in Azure is called a Resource Group. 

25. ### Unique Benefits of Government Cloud on Azure

- If you are considering the unique benefits of using the Government cloud on Azure, here are two key advantages:

    - Dedicated Regions for Data Isolation: Azure Government cloud provides dedicated regions that are physically isolated from non-government cloud regions. This ensures that data and workloads are isolated to meet specific government regulatory and compliance requirements.

    - Screened Personnel: The Azure Government cloud employs personnel who have undergone rigorous background checks and screening processes to ensure they meet high security and compliance standards required by government entities.

26. ### Premium file shares

If you need a performance option for an Azure storage account to provide cloud-hosted file server functionality for a high-performing Linux application that requires NFS file shares, you should choose Premium file shares.

27. ### Account with a Known Identity Provider

- If you need to provide external guest access to your Azure tenant for a consultant who will use their existing identity credentials, the consultant needs an account with a known identity provider.

29. ### Horizontal Scaling

- If you have a pool of identical virtual machines behind a load balancer and add more virtual machines to meet increased customer demand, this demonstrates Horizontal Scaling.

30. ### Examples of Platform-as-a-Service

- Two examples of Azure services that are Platform-as-a-Service (PaaS) solutions are:
    - Azure App Service: provides an environment for hosting applications without the need for managing the underlying operating system, including its maintenance and configuration.
    - Azure Container Instances: allows users to run containers without managing the underlying virtual machines or infrastructure, focusing on application deployment and management.

31. ### Scalability

- If your organization needs a cloud attribute that allows an application to automatically increase and decrease compute capacity to meet fluctuating demand without incurring unnecessary costs, the attribute you are referring to is Scalability

32. ### From CapEx to OpEx

- If your company plans to migrate to cloud services to avoid upfront hardware costs and pay only for the resources used, this shift in spending represents a move from CapEx (Capital Expenditure) to OpEx (Operational Expenditure).

33. ### Infrastructure as a Service (IaaS)

- If your company is migrating an internal web application to the cloud and requires specific configuration changes within the operating system, the most suitable cloud deployment solution is Infrastructure as a Service (IaaS).

34. ### SaaS Responsibilities in the Shared Responsibility Model

- If you are using a Software as a Service (SaaS) product, according to the Shared Responsibility Model, you are responsible for managing Information and Data and Devices and Accounts, while the cloud vendor is responsible for managing Application Management and Operating System Management.

35. ### Capital Expenditure (CapEx)

- When a company decides to build its own datacenter, involving expenses like purchasing the building and the necessary hardware, this represents a Capital Expenditure (CapEx) model.

36. ### Consumption-Based Model

- In cloud computing, the consumption-based model aligns with Operational Expenditure (OpEx)

37. ### Horizontal Scaling

- The following statements are true about horizontal scaling:

    - Horizontal scaling can occur automatically with no manual interaction.

    - Horizontal scaling adds additional copies of a resource, like a VM or container, to a resource pool.

    - Horizontal scaling does not require downtime.

38. ### Software as a Service (SaaS) Cloud Services

- The service provider will take care of the app's infrastructure, including servers, storage, and networking. They will also manage the app's software, including updates and security patches.

39. ### Vertical Scaling

- The action of increasing the capacity of a single virtual machine (VM) from two CPUs and 8 GB RAM to four CPUs and 16 GB RAM is an example of Vertical Scaling.

40. ### Infrastructure as a Service (IaaS)

- The cloud model that allows you to have complete control over the operating system is Infrastructure as a Service (IaaS).