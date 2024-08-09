# Microsoft Azure AZ900 - Management and Governance

## Paper 1

1. ### Delete Lock on VM

- A delete lock ensures that the VM cannot be accidentally deleted but still allows changes to its configuration, such as resizing. This is the most appropriate way to safeguard against deletion while maintaining operational flexibility.

2. ### Azure Resource Manager Templates

- ARM templates allow you to define the infrastructure and configuration for your Azure resources in a declarative JSON format. This approach enables you to consistently deploy multiple, identical environments with the same set of resources, ensuring uniformity and simplifying management. ARM templates are ideal for automating and managing the deployment of Azure resources.

3. ### Azure Cost Management Tool

- The Azure Cost Management tool helps organizations monitor, allocate, and optimize their cloud spending. It provides detailed insights into resource usage and costs, enabling automated budget setting, cost analysis, and alerting when spending exceeds predefined thresholds. This tool is essential for effective financial governance and cost control in the cloud.

4. ### Azure Cost Management Features

- _Budgets_: Azure Cost Management allows you to create budgets to proactively manage and monitor your cloud spending, helping to stay within financial targets.
- _Recommendations_: The tool integrates with Azure Advisor to provide recommendations for cost-saving opportunities.
- _Alerts_: You can set up alerts for unexpectedly high expenses, ensuring that you are notified when spending exceeds predefined thresholds.

5. ### Azure Policy

- Azure Policy is a service that enables you to create, assign, and manage policies to enforce compliance and governance across your Azure resources. It allows you to define rules and standards for your resources, ensuring they meet corporate and regulatory requirements. Azure Policy can be applied across multiple subscriptions for consistent policy enforcement and compliance tracking.

6. ### Azure Portal

- The Azure portal is a web-based interface that allows you to manage and configure your Azure resources. Since it is accessible through a web browser, you can use it on an iPad to create and manage virtual machines without needing to install any additional software.

7. ### Microsoft Purview

- Microsoft Purview is a comprehensive data governance solution that helps organizations map, catalog, and understand their data assets across various environments, including on-premises, multi-cloud, and SaaS. It provides data discovery, data classification, and data lineage capabilities to ensure data is managed and used effectively and in compliance with regulations.

8. ### Service Trust Portal

- The Service Trust Portal provides information about Microsoft's security, privacy, and compliance practices. It includes resources such as audit reports, compliance guides, and trust documents that detail how Microsoft secures its cloud infrastructure to meet various compliance standards.

9. ### Resource Locks in Azure

- Resource locks are used to protect your critical Azure resources from accidental deletion or modification. You can apply two types of locks:
- Resource locks can be applied at the subscription, resource group, or individual resource level, ensuring that essential resources remain protected regardless of the level of access or changes attempted.
- Delete lock: Prevents deletion of the resource.
- Read-only lock: Prevents any modifications to the resource.

10. ### Azure Monitor

- Azure Monitor provides a full-stack monitoring solution for collecting, analyzing, and acting on telemetry data from Azure and on-premises environments. It helps you maximize the availability and performance of your applications and services by offering comprehensive visibility into your resources and enabling proactive identification and resolution of issues.

11. ### Azure Reserved Virtual Machine

- Azure Reserved Virtual Machine Instances allow you to sign on for a 1- or 3-year commitment for a long-running virtual machine that can save up to 70% compared to month-to-month pricing.

12. ### Azure Service Health

- Azure Service Health provides a personalized view of the health of your Azure services and regions. It offers detailed insights into service issues, planned maintenance, and health advisories, allowing you to check for any broader Azure service issues that could be affecting your DB instance.

## Paper 2

13. ### Azure Cost Management

- If you need an all-in-one view of the current and predicted costs of your Azure resources spread across multiple resource groups, you should use Cost Management.

- Azure Cost Management is a comprehensive tool that provides insights into your current spending and forecasts future costs across all Azure services and subscriptions. It allows you to analyze your resource usage, set budgets, and optimize your cloud spending by providing detailed reports and cost predictions.

14. ### Azure Cloud Shell

- If you need to launch Azure Cloud Shell, you can do so from the Azure portal.

15. ### Application Insights

- If your website is experiencing errors and performance issues, the recommended Azure tool to troubleshoot errors and performance bottlenecks is Application Insights.

16. ### Azure Advisor

- If you need to identify underutilized and idle Azure resources to help reduce overall spending, the tool you should use is Azure Advisor.

17. ### Read-Only Lock

- If you need to prevent modifications to the configuration of a critical VM and prevent accidental deletion, you should apply a read-only lock on the VM.

18. ### Azure TCO Calculator

- If you need to compare costs and estimate potential savings from migrating an existing server cluster to Azure VMs and a server-hosted application to Azure App Service, you should use the Azure TCO Calculator.

19. ### Azure Arc

- If you need to manage and govern VM servers in both Azure and AWS using Azure-native services, you should implement Azure Arc to manage and govern AWS servers within Azure.

20. ### Application Insights

- If you need to view performance metrics and customer usage for your website, the Azure service that can help with this is Application Insights.

21. ### Log Analytics Workspace

- If you want to view a historical analysis of CPU utilization metrics for your Azure VMs to find trends over time, you should send the CPU utilization metrics to a Log Analytics workspace and then run a query within Log Analytics to view trends over time.

22. ### Pricing Calculator

- If your organization is planning to deploy a virtual machine workload and wants to estimate the costs of the virtual machines for this workload, you should use the Pricing Calculator.

- The Azure Pricing Calculator is a tool that allows you to estimate the costs of Azure services, including virtual machines. You can configure the specific details of your VM workload, such as the number of VMs, region, operating system, and other parameters, to get an accurate cost estimate.

23. ### Azure Cloud Shell

- In the Azure Cloud Shell, the two command-line environments available for use are:

    - PowerShell
    - Bash

24. ### Kusto Query Language (KQL)

- The query language used by Log Analytics is called KQL (Kusto Query Language).

- Kusto Query Language (KQL) is a powerful language designed for querying and analyzing large volumes of data in Azure Log Analytics, Application Insights, and other Azure services. It provides advanced querying capabilities to filter, summarize, and visualize data efficiently.

## Paper 3

25. ### Azure Monitor

- If you need a service that includes Log Analytics, Azure Monitor alerts, and Application Insights, you should use Azure Monitor.
- Azure Monitor acts as a wide-ranging surveillance tool that aggregates, scrutinizes, and reacts to telemetry data from your cloud-based and on-site infrastructures.

26. ### Microsoft Purview

- If a multinational corporation needs a solution to provide a unified view of data governance, ensure compliance with international data regulations, and enhance data discovery and insights across multiple cloud environments and on-premises data centers, they should enable and integrate Microsoft Purview.

27. ### Operating Systems Supporting Azure CLI and Azure PowerShell

- If you need to know which operating systems can have both Azure CLI and Azure PowerShell installed, the supported operating systems are macOS, Linux, and Windows.

28. ### Azure Advisor

- Azure Advisor is designed to provide the following functionalities:

    - View Operational Excellence Recommendations: Azure Advisor provides best practices and recommendations to help you improve your operational processes and achieve operational excellence in managing your Azure resources.
    - Recommend Cost Savings for Existing Resources: Advisor analyzes your resource usage and provides recommendations for cost savings, such as suggesting the purchase of reserved instances for long-running virtual machines (VMs), which can significantly reduce costs【
    - Identify Steps to Improve Your Security Posture

29. ### Pricing Calculator

- If your CFO needs an estimate of the monthly costs of running an internal application with Azure App Service, you should use the Pricing Calculator.

30. ### Azure Resource Manager

- If you need to identify the Azure component responsible for all interactions with Azure, including the Azure portal, programmatic access, and command-line interaction, it is Azure Resource Manager (ARM).

31. ### Azure Monitor Alerts

- If you need to automatically notify your  team whenever CPU utilization on a business-critical Azure VM rises above 90% for over 5 minutes, you should use Azure Monitor Alerts.

32. ### Tags

- If you need a consistent method to track which office and department is using which Azure resources for cost tracking, the preferred method is to use Tags.

33. ### Azure Arc

- If you want to implement the "single pane of glass" functionality of Microsoft Defender for Cloud for your Azure, AWS and on-premises resources, the required prerequisite is that AWS and on-premises resources must first have Azure Arc enabled.

- Azure Arc is the standard method of integrating non-Azure resources with Azure management tools and is a prerequisite to integrate external locations with Microsoft Defender for Cloud.

34. ### Alert Rule and Action Group

- If you need to configure Azure Monitor alerts, the required components are Alert Rule and Action Group.

35. ### Enable Azure Arc on Your On-Premises Servers

- If you need to run Azure serverless services, like Logic Apps, on your on-premises servers, the preferred method is to enable Azure Arc on your on-premises servers.

36. ### Spot Virtual Machines

- If you are looking to decrease costs for a non-business-critical workload on Azure, you should use Spot Virtual Machines, which can provide cost savings of up to 90% compared to on-demand pricing.