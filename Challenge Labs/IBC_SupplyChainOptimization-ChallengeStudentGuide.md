<!-- 
![](--logo link-- 'Microsoft Industry-Based Challenges')
-->

# Industry-Based Challenges: Supply Chain Optimization  

## Challenge lab student guide  

### March 2021 

Information in this document, including URL and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The names of manufacturers, products, or URLs are provided for informational purposes only and Microsoft makes no representations and warranties, either expressed, implied, or statutory, regarding these manufacturers or the use of the products with any Microsoft technologies. The inclusion of a manufacturer or product does not imply endorsement of Microsoft of the manufacturer or product. Links may be provided to third party sites. Such sites are not under the control of Microsoft and Microsoft is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. Microsoft is not responsible for webcasting or any other form of transmission received from any linked site. Microsoft is providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement of Microsoft of the site or the products contained therein.

© 2020 Microsoft Corporation. All rights reserved.

Microsoft and the trademarks listed at <https://www.microsoft.com/legal/intellectualproperty/Trademarks/Usage/General.aspx> are trademarks of the Microsoft group of companies. All other trademarks are property of their respective owners.


# Supply Chain Optimization challenge lab student guide

## Abstract and learning objectives

Parts Unlimited, a subsidiary of Fabrikam Retail INC., has been feeling some pain and would like your help to redesign and implement some new solutions to be able to better compete in the current marketplace.  Among the main problems that Parts Unlimited is facing are 

*   Lack of connection between online and in-store data leading to an inability to provide a selection optimization that is tailored to a specific customer
*   Lack of infrastructure to maximize cost savings through correct inventory levels
*   Poor last-mile delivery
*   Departments operate in silos so they cannot communicate due to disparate data sources.
*   Limited visibility of data with no feedback loop on the supply chain.
*   Affecting changes to the supply chain is not a trivial endeavor. 
*   No current 360 degree view of the supply chain. 

To remedy this situation, Parts Unlimited is asking you to build a system that takes all of the supply-chain data and ingests it into IoT and Event Hubs as necessary, then performs analysis on the data.

Key success criteria will include 

*   Contract Cycle data and optimization
*   Available to promise capabilities
*   Price-elasticity analysis
*   Route planning and scheduling
*   Demand forecasting

Included in the analysis and processing will be data from 
*   Point of sale transactions
*   Purchase data from all channels
*   Device/Sensor data from IoT devices
*   Warehouse logistical and operational data
*   Social media sentiment and analysis

The primary goal for this system is to conglomerate all of the data into a single source of truth for use in reporting, bringing together all of the moving pieces from the supply chain.  

In the end, your solution should provide a vision that allows the audience (the Chief Marketing Officer, Chief Digital Officer, the Chief Data Officer, and the Customer Experience Manager) to understand how using this solution will give the information that is needed to deliver a 360 degree view of the supply chain.

## Customer case study

### Customer situation

Parts Unlimited Retail, Inc has been selling goods through various retail channels for the past 15 years.  As various platforms and technologies have evolved, Parts Unlimited has struggled to keep up, but has done the best they could to continue to provide solutions for their customers.  

Currently, they have just over 200 brick-and-mortar stores but are planning to close 50+ of these stores next year, taking the number of physical locations down to 150 stores due to declining revenue and various other factors.  Of the remaining 150 stores, 35 of them are currently streamlined for an attempted re-branding that happened a few years ago.  The re-branded stores were chosen based on population bases of less than 50,000 in an 200 square mile radius or within 50 miles of a major metropolitan area. These rebranded "Parts Unlimited Hometown" stores eliminated most of the non-essential retail, such as sporting and workout equipment, and focused in on essentials like appliances, automotive, and kept a limited selection of electronics, only offering about 15% of the options for items like UHD televisions, antennas, and blu-ray players.  Customers have expressed frustrations when an advertisement in the local newspaper for Parts Unlimited included a great deal on a large-screen television only to find they have to order online or drive to the larger store in a city that is sometimes located over 50 miles away.  While it is clear that customers are not pleased with this solution, it is not clear if this is an effective strategy to save the company when it comes to providing a simplified retail option. 

In addition to re-branding efforts, in the past few years attempts have been made to enhance the web app for responsive delivery and a couple of apps were also built to specifically target IOS and Android devices. Unfortunately, the data from these applications and the web solution is not connected, and when a user switches devices or goes from a device to the web, the experience is not uniform, leading to confusion and frustration.  Questions such as "why isn't the item I selected on my phone in my cart when I go to the website?" are far too common.    

Parts Unlimited needs an ability to collect and analyze all of this data in order to make the best uniform solution possible.   The final solution from this challenge workshop should provide an ability for Parts Unlimited to take control of their supply chain so that customers can know when and where products are going to be available, and that stores can be prepared to keep up with expected demands.  

While there are clearly other issues at play that Parts Unlimited needs to solve, the solution you are creating in this workshop needs to allow for a user to be able to walk into a brick-and-mortar store and get the items they are looking for, and for the stores to have the ability to meet demand based on an optimized supply chain. 

This goal of improved ability to meet customer demand will be accomplished by establishing a 360 degree view of the supply chain, with data analysis and reporting that provides the business the ability to plan and schedule deliveries of products according to forecasted needs, based on customer sentiment current buying trends.

#### Customer's current process

Parts Unlimited currently has over 200 brick-and-mortar stores, with 50+ stores closing and 35 stores running the re-branded profile.  Some stores have a pre-determined, limited selection and a limited inventory of the products they do offer. 

Parts Unlimited has an MVC website written in the .Net Framework and has been previously upgraded to version 4.72. The website is supposed to be responsive, as it utilized Bootstrap for responsive layout, but the site is currently not able to work on a few devices due to some styling problems.  

In addition to the website, Parts Unlimited has an Android application written in native Java that is three versions behind the current version of Android, but has been upgraded enough to continue to work on newer devices, even though it does not necessarily leverage all of the features of newer devices.  

Along with the website and android app, a third app written in Swift is available for use on the Apple IOS devices.  

All applications and sites do work, but the user experience, including sign-on, shopping cart, and other factors is unique to each platform.  For example, a user must sign in on the website and then sign in again on the device, and the shopping cart is not shared across devices, so items added to the cart on the web do not show up on the phone, or vice-versa.

As a struggling retailer, Parts Unlimited has a limited amount of resources to apply to getting the entire experience upgraded, so they need you to come up with the best, cost-effective solution.   

When it comes to supply chain management, Parts Unlimited is not very efficient.  They currently have five different departments, all siloed, and none of the departments are working together to get to the overall vision that Parts Unlimited needs.  This is in addition to separate databases used to track products, orders, and customers for the online and the physical store inventory and ordering systems.

The current reporting systems live on top of four different systems with five total silos.  They are as follows:

*   SAP for Demand Planning
*   SAP for Financials
*   Salesforce CRM
*   JD Edwards EDI
*   Oracle Retail ERP

### Current Process  

Current Customer buying solutions:  

![High level view of the current process](media/sco/CurrentProcess.png 'Current process diagram') 

Current supply chain reporting:  
![High level view of the supply chain vision](media/sco/CurrentSupplyChainManagementProcess.png 'Current process diagram') 

### Customer needs

1.  Use Azure data and analytics tools to create a 360 degree view of the supply chain.

2.  Ingest data from existing systems as defined, as well as other systems and future implementations (i.e. IoT Devices, Website and app telemetry for customer search and purchase data).  Data from point of sale transactions and purchase information should also be ingested.  

3.  Provide reporting to the business user to be able to make decisions around the contract cycle, delivery scheduling and route planning, and demand forecasting with price-elasticity metrics.

4.  Optimize warehouse inventory management and staff utilization to ensure all channels are working with efficiency and no under-staffing or over-staffing according to predicted demands.

5.  An optimized last-mile delivery plan to ensure that customers are getting their orders as quickly as possible.  

6.  An ability to use feedback in any step of the process, as well as give feedback based on findings.  

7.  Because the solution has optimized the supply chain, it will also be possible to optimize the customer return process to expedite returns and getting the products back on the shelves to be sold to other customers.  

### Infographic for common scenarios
 
![Infographic for common scenarios](media/sco/common-scenarios-iot.png 'Common scenarios diagram') 

_High-level architecture_

1. Without getting into the details (the following sections will address the particular details), diagram your initial vision for handling the top-level requirements for 

*   Identification of data sources
*   Ingestion of streaming data from sources
*   Organization and/or filtering of data
*   Creating the expected reports
*   Presentation of data to the business users

## Challenge 1: Build the architecture for collecting and ingesting (extract) data

_Data ingest_

1. What are your recommended options for ingesting payment transaction events and customer browsing and shopping data as they occur in a scalable way that can be easily processed?

2. Of the ingest options you identified previously, which would you recommend for Parts Unlimited's scenario?


## Challenge 2: Build the architecture for loading and transforming data

_Data transformation_

1. Will data transformation be needed?

2. If so, Which option would you recommend and why?  

3. Will there need to be a hot and a cold path on this data? 

_Data processing_

1. How will you filter the data to get relevant information?

2. How will you ensure that data processes are repeatable?


## Challenge 3: Build the architecture for presenting the data

_Dashboards and reporting_

1. Parts Unlimited's business analysts would like to have a set of dashboards they can monitor that provide real-time views of supply chain data. What do you propose using to meet this requirement? Be specific about how this solution will be put in place and which features it supports, and why it will be useful to the business analysts.

2. Parts Unlimited's marketing team would like to be able to get insights from the data, and be able to identify trends, as well as see how effective various pricing strategies are.   How will you provide this data to them to enable them to ensure an optimal customer experience?


## Additional references

| **Description**                                        | **Links**                                                                                                                         |
| ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| Create a data factory                              | <https://docs.microsoft.com/en-us/azure/data-factory/quickstart-create-data-factory-portal>                                                                         |
| Load data into Azure Data Lake Storage from Azure Data Factory               | <https://docs.microsoft.com/en-us/azure/data-factory/load-azure-data-lake-storage-gen2>                                                                         |
| Azure Data Explorer data ingestion overview        | <https://docs.microsoft.com/en-us/azure/data-explorer/ingest-data-overview>                                                                         |
| What is Azure Databricks        | <https://docs.microsoft.com/en-us/azure/databricks/scenarios/what-is-azure-databricks>                                                                         |
| Azure Synapse Analytics        | <https://azure.microsoft.com/en-us/services/synapse-analytics/>                                                                         |
| Using Synapse analytics from Databricks        | <https://docs.microsoft.com/en-us/azure/databricks/data/data-sources/azure/synapse-analytics>                                                                         |
| Using SQL file metadata in synapse analytics        | <https://docs.microsoft.com/en-us/azure/synapse-analytics/sql/query-specific-files>                                                                         |
| Cosmos Db        | <https://azure.microsoft.com/en-us/services/cosmos-db/>                                                                         |
| Azure Machine Learning       | <https://azure.microsoft.com/en-us/free/machine-learning>                                                                        | 
 IoT Hubs                             | <https://docs.microsoft.com/en-us/azure/iot-hub/about-iot-hub#:~:text=IoT%20Hub%20is%20a%20managed%20service,%20hosted%20in,of%20IoT%20devices%20and%20a%20cloud-hosted%20solution%20backend.>                                                                             |
| Azure IoT Edge                             | <https://azure.microsoft.com/en-us/services/iot-edge/>                                                                             |
| Azure IoT Device Provisioning Service                            | <https://docs.microsoft.com/en-us/azure/iot-dps/about-iot-dps>                                                                             |
| Event Hubs                             | <https://azure.microsoft.com/en-us/services/event-hubs/?OCID=AID2100131_SEM_cad070d74e92111e5f782f066421fc39:G:s&ef_id=cad070d74e92111e5f782f066421fc39:G:s&msclkid=cad070d74e92111e5f782f066421fc39>                                                                         |
| Event Grid              | <https://docs.microsoft.com/en-us/azure/event-grid/overview>                                                                         |

