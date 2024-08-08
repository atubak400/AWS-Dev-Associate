# Microsoft Azure AZ900 - Architecture and Services

## ## Paper 1

1. ### Azure Subscriptions

- An Azure subscription is the primary billing entity for Azure resources. It defines the level of access and control you have over the resources you provision and manage within that subscription. All usage and associated costs are tied to the subscription, making it the central unit for managing billing and cost tracking.

2. ### Log Analytics Workspace

- A Log Analytics Workspace in Azure is a central repository that collects and stores log and performance data from various Azure resources and services. This workspace allows you to analyze, visualize, and gain insights from this data using queries, helping with monitoring, troubleshooting, and ensuring the health and performance of your environment.

3. ### Azure Arc

- Azure Arc extends Azure management and governance capabilities to on-premises, multi-cloud, and edge environments. It allows you to manage and govern virtual machines, Kubernetes clusters, and databases consistently across diverse environments, providing unified operations, security, and compliance across your entire infrastructure.

4. ### Kusto Query Language (KQL)

- Kusto Query Language (KQL) is used for writing queries in Azure Log Analytics. It is a powerful query language designed to work with large datasets and allows you to perform complex querying, filtering, and data analysis within Azure Monitor logs, Application Insights, and other Azure services.

5. ### Azure Automation

- Azure Automation is designed to automate the deployment, configuration, and management of Azure resources, including Virtual Machines, SQL Databases, and Azure Web Apps. However, it does not directly manage physical on-premises servers.

6. ### Azure Service Health

- Azure Service Health provides a personalized view of the health of your Azure services and regions. It consists of three key areas:

  - Azure Status: Displays global health information about Azure services and regions, informing you of major issues affecting many customers.
  - Service Health: Offers personalized information about the health of Azure services and regions you are using, including outages, planned maintenance, and other health advisories.
  - Resource Health: Provides detailed information about the health of individual Azure resources, helping you diagnose and resolve issues that are specific to your resources.

7. ### Azure Automation Service

- Azure Automation is designed to automate the deployment, configuration, and management of Azure resources. It helps you reduce the complexity and manual effort required to manage your cloud and on-premises infrastructure. Azure Automation can automate tasks such as the deployment of virtual machines, updates, and compliance management, improving operational efficiency and consistency.

8. ### Azure Subscriptions

- An Azure subscription is the primary billing entity for Azure resources. It defines the level of access and control you have over the resources you provision and manage within that subscription. All usage and associated costs are tied to the subscription, making it the central unit for managing billing and cost tracking.

9. ### Premium Block Blobs

- For storing small, frequently accessed blob objects, Premium block blobs offer the best performance with high throughput and low latency. This makes them ideal for use cases like training machine learning models where quick and frequent access to data is essential.

10. ### Conditional Access Policy

- Conditional Access policies in Azure Active Directory (Azure AD) allow you to define and enforce access controls based on specific conditions. You can configure policies to require MFA for all users or specific groups, ensuring a secure and consistent authentication process across your organization. These policies help protect access to your cloud apps and data by adding an extra layer of security.

11. ### Azure VPN Gateway

- If you are designing a hybrid network in which your Azure virtual network needs to establish a secure and private connection to your on-premises network via an IPsec tunnel over the public internet, you should use Azure VPN Gateway. This service creates secure site-to-site VPN connections using IPsec/IKE protocols, ensuring encrypted and private communication between your Azure and on-premises networks.

12. ### Azure Regions

- If you are considering the benefits of using Azure regions, here are three key advantages:

  - Azure regions are distributed globally: This global distribution allows you to deploy applications and services close to your users, reducing latency and improving performance.

  - Regions provide fault tolerance and can often withstand complete data center failures: Each region consists of multiple data centers, providing redundancy and ensuring high availability even in the event of a data center failure.

  - Data residency is honored within each region: Azure regions ensure that data residency and compliance requirements are met by keeping data within specified geographical boundaries.

13. ### Zero trust

- If you are considering the advantages of the Zero Trust security model, here are two key benefits:

  - Reduces the risk of unauthorized access by implementing strict access controls: Zero Trust requires verifying every access request as though it originates from an open network. It enforces strict access controls and minimizes the risk of unauthorized access by continuously monitoring and validating user identity and permissions.

  - Validates trust before granting access, regardless of the user's location: Unlike traditional security models that rely on securing the network perimeter, Zero Trust validates every access attempt, whether it comes from inside or outside the organization. This approach ensures that trust is established through verification, not assumed based on location.

14. ### File service in a storage account

- If you need to create a network drive in Azure that is accessible from multiple Windows 11 computers, you should use Azure Files. Azure Files provides SMB (Server Message Block) protocol support, which allows you to create a fully managed file share in the cloud that can be mounted as a network drive on Windows machines.

- While Azure Blob Storage is useful for object storage and scenarios involving unstructured data, it does not support direct SMB protocol access needed for mounting as a network drive on Windows.

15. ### Billing Segmentation

- If your organization needs to segment billing between various departments, such as marketing and human resources, you should create a separate subscription for each department under your Azure account. This method provides the best way to manage costs independently, assign specific budgets, and monitor expenses for each department.

16. ### Azure Region Pairs

- Azure region pairs consist of two regions within the same geography that are strategically located within the same geography (at least 300 miles apart) to provide disaster recovery and data residency.

17. ### Azure Functions

- If your company needs a cost-effective compute solution for handling data processing tasks triggered by HTTP requests, with the requirement to start instantly and terminate upon job completion to avoid unnecessary charges, you should use Azure Functions.

18. ### Authentication

- If you need to ensure that users of your application are who they say they are, you should use Authentication.

19. ### Benefits of using Subnet in Azure Virtual Network

- If you are looking at the benefits of using subnets within your Azure Virtual Network, here are two key advantages:

  - IP Address Allocation on the Subnet is More Efficient: Using subnets allows for efficient IP address allocation within segmented parts of the virtual network, aligning address spaces with organizational structure or application architecture. This helps in managing IP addresses more effectively and reducing wastage.

  - You Can Logically Group Services on the Same Virtual Network: Subnets allow for the logical grouping of services, enabling organized network traffic management. This facilitates associating closely related services within the same network segment, simplifying management and improving security.

20. ### Role-Based Access Control (RBAC)

- If you are setting up Role-Based Access Control (RBAC) in Azure, the three necessary components for any RBAC assignment are:

  - Scope: This defines the set of resources that the access applies to. It can be at the level of a management group, subscription, resource group, or a specific resource.

  - Security Principal: This is the entity that requires access. It can be a user, group, service principal, or managed identity.

  - Role Definition: This is a collection of permissions. It specifies what actions can be performed on the resources within the specified scope. Examples include roles like Reader, Contributor, or Owner.

21. ### Azure App Service

- If you need to host web apps without managing the underlying infrastructure, you should use Azure App Service.

- Azure App Service is a fully managed platform for building, deploying, and scaling web apps. It abstracts the underlying infrastructure, allowing you to focus on application development and management without worrying about the physical servers or virtual machines.

22. ### Management Groups.

- If managing access control to multiple Azure subscriptions associated with a single Azure AD tenant is becoming cumbersome, you should use Management Groups.

- Management groups can be used to organize our subscriptions into an organizational hierarchy, so that we can granularly manage things, such as access control to the various subscriptions associated with our Azure AD tenant.

23. ### Azure ExpressRoute

- If you need to establish a secure and private connection between your Azure virtual network and your on-premises network via a high-speed leased line that does not traverse the public internet, you should use Azure ExpressRoute.

## Paper 2

24. ### Azure Files

- If you need to migrate the functionality of your existing on-premises file server to Azure and require a solution that supports Server Message Block (SMB) shares for file storage and management, you should use Azure Files.

25. ### Migrating an application requiring NTLM authentication

- If you need to migrate an application requiring NTLM authentication to Azure while retaining your existing Active Directory domain/namespace, you should configure an Azure VM with Windows Server to operate as an Active Directory domain controller. This setup allows the application to authenticate with your VM-hosted AD server, ensuring compatibility with the NTLM protocol.

26. ### Ultra Disks

- If you need to create a virtual machine with a disk that can hold up to 64 TB and provide the highest possible performance with sub-millisecond latency, you should select the Ultra Disk type.

27. ### Infrastructure Design for High Availability

- If you need your Azure infrastructure to continue functioning if a single datacenter goes offline, while keeping latency and performance optimized within the same region, you should replicate your infrastructure across multiple availability zones in that region.

28. ### Defense in Depth

- If you are looking for a security strategy that layers multiple stages of protection, such as physical security, network security, application security, etc., to create a robust defense against cybersecurity threats, the concept you are referring to is Defense in Depth.

29. ### Azure Container Instances (ACI)

- If you need to run an application with the requirements that all software dependencies are bundled with the application source code, the application is portable, compute is provisioned and run only when needed to save costs, and there is minimal management overhead, you should choose Azure Container Instances.

30. ### Azure Premium Performance Options

- When choosing Azure's premium performance options for storage accounts, consider the following:

  - Premium performance options are limited to a specific storage type.

  - Premium performance options do not support all redundancy types.

  - Premium performance options cost more than the standard general-purpose v2 performance type.

31. ### Zero Trust

- If you are referring to the security model that assumes all users are untrustworthy until they prove otherwise with a valid identity, the model is known as Zero Trust.

32. ### Secure IPsec tunnel

- To create a secure IPsec tunnel over the public internet from an Azure virtual network to an on-premises location, you need the following three Azure components:

  - Gateway Subnet: This is a specific subnet in your virtual network dedicated to hosting the virtual network gateway. It is crucial for enabling the VPN gateway to manage the IPsec tunnel.

  - Local Network Gateway: This represents your on-premises location in Azure. It specifies the IP address of the VPN device in your on-premises network and defines the on-premises IP address ranges that the Azure VPN gateway will connect to.

  - Virtual Network Gateway: This is the VPN gateway that facilitates the creation of the IPsec tunnel. It provides connectivity between your Azure virtual network and your on-premises network through a secure VPN connection.

33. ### Secure IPsec tunnel Analogy

- Imagine you're sending a secure package from your house (Azure virtual network) to a friend's house (on-premises location) across town, and you need to use a courier service to make sure it gets there safely.

  - Gateway Subnet: Think of this as the courier's dispatch center at your house. It's a specific area where the courier gathers everything needed to start the delivery process. Without this starting point, the courier wouldn’t know where to begin.

  - Local Network Gateway: This acts like your friend's address and the security instructions you give to the courier. It tells the courier exactly where to go and what security checks need to happen at your friend’s end. It includes the address of your friend's house and any special instructions for delivering the package securely.

  - Virtual Network Gateway: This is the actual courier service that carries your package safely from your house to your friend's house. It ensures that the package is transported securely and reaches the correct destination without being tampered with.

  - In this analogy,
  - Your house is the Azure virtual network.
  - The courier's dispatch center (Gateway Subnet) prepares and coordinates the delivery from your side.
  - The friend's address (Local Network Gateway) provides the courier with details about the destination and ensures it can safely connect with your friend's house.
  - The courier service (Virtual Network Gateway) is the secure connection that transports your package from your house to your friend’s house, ensuring it arrives safely and securely.
  - By working together, these three components ensure that your data travels securely from Azure to your on-premises location, just like how the courier ensures your package is delivered safely to your friend.

34. ### Subscription

- The Azure organizational component that associates a billing account with your Azure environment is a Subscription.

35. ### General-purpose v2

- If you need to host multiple storage formats in an Azure storage account while keeping costs low and maintaining an acceptable level of performance, you should choose General-purpose v2.

## Paper 3

36. ### Azure Active Directory Domain Services (Azure AD DS)

- For a company migrating their existing applications to Azure that require classic Active Directory features such as Group Policy and LDAP, while retiring all on-premises resources and ensuring a managed identity solution for authentication, the best solution is to utilize Azure Active Directory Domain Services (Azure AD DS)

37. ### Blob Storage in a Storage Account

- For storing large amounts of directly-accessible data, including image files, videos, and backup files, the optimal Azure service to choose is Blob Storage in a Storage Account.

38. ### Cosmos DB:

- NoSQL Database: Designed for globally distributed, highly responsive NoSQL databases, not ideal for storing large media files and backups

39. ### Cool Storage Tier

- For long-term storage of security video footage that is accessed infrequently but must be readily available when needed, you should store video files using the Cool Storage Tier in Azure Blob Storage. This tier is designed for data that is infrequently accessed but needs to be available immediately when required, offering a cost-effective solution for such use cases.

40. ### Archive Storage Tier

- For long-term storage of server logs that are expected to be accessed infrequently (at most once per year) and do not need to be immediately accessible, you should store the server logs using the Archive Storage Tier in Azure Blob Storage. This tier is designed for data that is rarely accessed and offers the lowest storage cost.

41. ### Azure File Sync

- To automatically synchronize the data from your on-premises file server with Azure Files for backup and disaster recovery purposes, and to enable remote users to access synchronized copies of mapped drives in Azure Files, you should use Azure File Sync.

42. ### Azure Migrate

- If your company is beginning their migration of on-premises servers to Azure and needs to plan the migration of several VMs and their hosted applications, including discovering app dependencies on other servers necessary for continuation of service, the best Azure service to use is Azure Migrate.

43. ### Azure China Regions

- Azure China regions have specific characteristics that differentiate them from other Azure regions globally:
  - An organization must be conducting business in China to be able to use an Azure China region.
  - Azure China regions are managed by a China-based third-party provider. Azure China regions are operated by 21Vianet, a China-based third-party provider, to comply with China's regulatory requirements. This unique operational model is distinct from Azure's global regions.

44. ### Virtual Machines

- If you need to migrate a Windows-based legacy on-premises application to Azure with minimal effort, the most suitable compute service to choose is Virtual Machines (VMs).
- While containers offer portability and scalability, migrating a legacy application to containers often requires significant changes to the application .

45. ### Azure Virtual Desktop

- To provide your company's employees with a flexible and secure remote working solution that allows access to company-specific applications and resources from various devices and locations, the best Azure service to use is Azure Virtual Desktop (AVD).

46. ### Geo-Redundant Storage (GRS)

- If you need to choose a redundancy option for a new storage account hosting business-critical data necessary for training a machine learning model, and you want to withstand a region failure while saving costs, you should choose Geo-Redundant Storage (GRS).

47. ### Availability Sets

- To ensure high availability of your critical line-of-business application in the event of hardware or software failures within an Azure data center, you should recommend using Availability Sets.

48. ### Private Endpoint and Disable Public Access

- To secure your Azure storage account that contains sensitive customer information, you should implement a private endpoint in in your azure virtual network that connects to the storage account and disable public access to the storage account.

49. ### Azure Virtual Machine Scale Sets

- Azure Virtual Machine Scale Sets let you create and manage a group of load balanced VMs. The number of VM instances can automatically increase or decrease in response to demand or a defined schedule.

50. ### Single Sign On (SSO)

- The Azure feature that allows you to sign in to third-party applications using your Azure AD credentials is called Single Sign-On (SSO).

51. ### Virtual Network Peering

- To create a secure, private connection between your Azure resources located in two different regions using only Azure's private network backbone, you should create a virtual network in each region and connect both networks with virtual network peering.

- Azure does not support a single virtual network spanning multiple regions. You must use multiple virtual networks and connect them

52. ### Azure Data Box

- For migrating over 60 TB of data from your on-premises file server to Azure Storage, you should use Azure Data Box. This service allows for an initial bulk offline data transfer, which can then be followed by subsequent transfers over the internet.
