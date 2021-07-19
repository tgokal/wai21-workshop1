# Hands-on-Lab 1: Create a Wordpress website hosted in Azure

**Duration**: 10-15 minutes

## Table of Contents
- [Learning Objectives](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#learning-objectives)
- [Our Goal and Background](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#our-goal-and-background)
- [Solution Architecture](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#solution-architecture)
- [Step-By-Step Guide](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#step-by-step-guide)
    - [Log into Azure Sandbox](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#log-into-azure-sandbox)
    - [Select Resource Groups](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#select-resource-groups)
    - [Create a Resource Group](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#create-a-resource-group)
    - [Enter information for Resource Group](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#enter-information-for-resource-group)
    - [Create Resource Group](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#create-resource-group)
    - [Provision Wordpress App](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#provision-wordpress-app)
    - [Create a New App Service Plan](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#create-a-new-app-service-plan)
    - [Create a mySQL Database](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#create-a-mysql-database)
    - [Test our App](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#test-our-app)
- [Congratulations!](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#congratulations-)
- [Delete Resource Group](https://github.com/tgokal/wai21-workshop1/blob/master/HOL/labs/HOL%201%20Create%20a%20Wordpress%20website%20hosted%20in%20Azure.md#delete-resource-group)

## **Learning Objectives**
Let's start off with the basics and a complete a familiar exercise - provisioning a resource, namely a Wordpress application that will be entirely hosted in Azure. Although we also provision a SQL Database and an Azure App Service, we won't be going into any of the details of this for HOL 1, but **rather walking through the motions of creating resources using Azure Portal**. Often, creating resource groups and resources follows the same underlying steps of fill out relevant information fields based on cost, location, scope and time.

## **Our Goal and Background**

Our goal is to provision a Wordpress Installation Azure Website that our users can use to install WordPress on their local device. We're going to achieve this by:

- Creating an Azure Subscription
- Provisioning an Azure Resource Group
- Provisioning a Wordpress website through an Azure Web App
    - Provision an Azure Web App Service plan
    - Provision a Azure SQL Database

## **Solution Architecture**

![Create a resource group](images/HOL1/0_solution_architecture.PNG)

## **Step-By-Step Guide**

### **Log into Azure Sandbox**

Once you've logged into your Azure sandbox, you'll arrive at the **Home Page of the Azure Portal**. 

![Home Page of Azure Portal](images/HOL1/1_homepage.PNG "Home page of Azure Portal")

### **Select Resource Groups**

Select **Resource Groups** 

![Create a resource group](images/HOL1/1a_resource_groups.PNG)

### **Create a Resource Group**

Select **Create** to provision a new resource group. 

![Create a resource group](images/HOL1/1b_resource_groups.PNG)

### **Enter information for Resource Group**

Enter in a Resource Group name and select the region which our Azure resources will be provisioned to. 

The closest our Region to where we are located is often the best Region to provision our resources since it will cost less as we egress data.

| **Resource Group Field**  | **What we Enter**  |
|---|---|
|  Subscription | `your_subscription`  |
| Resource Group  | `rg-wai-intro2azure-{suffix}`  |
|  Region |  `Australia East` |

![Create a resource group](images/HOL1/1c_create_rg.PNG) 

Once completed, we can pass through **Validation** of our Resource Group. This checks whether our Resource Group name is globally unique and if the Region we've selected is available. 

![Create a resource group](images/HOL1/1d_validation.PNG)

Select **Create** to provision our Resource Group. We'll be redirected to the Resource Groups page and on the top right corner, we'll have received a notification to say that our Resource Group has been successfully created.

![Create a resource group](images/HOL1/1e_resource_group_created.PNG)

### **Create Resource Group**

If we select our Resource Group, we can now **Create resources** by selecting the bottom blue button. 

![Create a resource](images/HOL1/2_create_resource.PNG) 

By doing so, we'll be redirected to the Azure Marketplace. 

![Azure Marketplace](images/HOL1/3_azure_marketplace.PNG) 

This is where we can provision Azure resources, like Azure Virtual Machines, Azure App Service and managed Azure SQL Databases, which is what we'll be doing later on. 

![Azure Marketplace resources](images/HOL1/4_azure_marketplace_lab_resources.PNG)

For now, we'll just provision a WordPress web application. 

### **Provision Wordpress App**

In the Search bar of Azure Marketplace, search for '**wordpress**'. 

![Searching for Wordpress resources](images/HOL1/5_search_wordpress.PNG) 

We can see a variety of different resources that create WordPress websites in various ways. 

From provisioning a VM with a WordPress image to deploying WordPress on Windows Server 2016, through to WordPress App Service, which is what we're wanting to provision today. 

![Variety of Wordpress resources](images/HOL1/6_wordpress_resources.PNG)  

Select the **WordPress App Service resource** and select **Create**. 

![Provisioning WordPress App Service](images/HOL1/7_wordpress_app.PNG)

We now need to create our WordPress Resource by providing the below information, like the name of our WordPress application, our resource group and database. 

![Creating a WordPress resource](images/HOL1/8_provision_wordpress.PNG)

| **Resource Field**  | **What we Enter**  |
|---|---|
| App name  | `wordpress{suffix}` |
|  Subscription | `your_subscription`  |
| Resource Group  | `rg-wai-intro2azure-{suffix}`  |
|  Database Provider |  `Azure Database for MySQL` |
|  App Service plan | {to be created below in Step 6}  |
|  Database | {to be created below in Step 7}  |

### **Create a New App Service Plan**

We need to **Create a New App** Service Plan which will inform the features of our Wordpress application (i.e. how much memory we have, the length of time we can use our App and how much we pay for use) By default, we see the below:

![Creating a new App Service Plan](images/HOL1/9_app_service_plan.PNG)

Accounting for cost of the resource by geographic location and pricing tier, we want to have these values changed to be:

| **Resource Field**  | **What we Enter**  |
|---|---|
| App Service plan  | `wordpress-app{suffix}` |
|  Location | `Australia East`  |
| Pricing Tier  | `F1`  |

Select **Pricing Tier**, select **Dev/Test** and then select `F1`. We select a pricing tier and compute type to match our workload, and often how much workload we will have in the future (i.e. scalability) will influence this. 

The **Dev/Test** category is one that developers use to test their model, or application in an environment which is built for less demanding workloads. In this case, since we're just creating our application to see what it looks like, this category is the most appropriate. 

For the `F1` tier, our App will be provisioned on shared infrastructure (i.e a VM which is shared with another user in the public cloud - don't worry they can't gain access to what we're provisioning!)
Often many organisations with private and confidential data will choose to provision dedicated infrastructure and compute resources. 

With our resource however, we have the restrictions of 1GB of memory and 60 minutes/day access to the website. 

![Select a free app service](images/HOL1/10_f1_app.PNG)

![Select a free app service](images/HOL1/11_f1_app.PNG)

### **Create a mySQL Database**

Next, we need to create a **Database** for our website's backend. A database is meant for storage and is another Azure resource which we can provision.

A backend is can be a piece of software or the physical hardware, and in our case is a database where any users enter into our website would be stored. 

Storage is another topic which we'll be covering in greater detail later on. For example, storaging the information our users enter into our website gives us the option of creating a machine learning model to forecast revenue or product demand. The possibilities of what we can do once we've stored our data are endless. 

![Select a free app service](images/HOL1/12_create_database.PNG)

| **Resource Field**  | **What we Enter**  |
|---|---|
| Server name | `wordpress{suffix}-mysqldbserver` |
|  Server admin login name | `mysqldbuser`  |
| Password  | `Enter password of your choice here`  |
|  Confirm Password |  `Re-enter password of your choice here` |
| Version | `5.7`  |
|  Pricing Tier | `General Purpose, 4vCore(s), 100GB`|
|  Database name | `mysqldb_{suffix}`|

![Select a free app service](images/HOL1/13_filled_details.PNG)

Once we select **Create**, we can see that our Deployment is in progress.

![Select a free app service](images/HOL1/14_deployment.PNG)

This should take 1-2 minutes and once it's provisioned, we'll see a **green tick**. 

![Select a free app service](images/HOL1/15_green_tick.PNG)

If we select **Go to resource**, we get redirected to the App homepage.

![Select a free app service](images/HOL1/16_app_homepage.PNG)

As we've spun up our App, we've also create our SQL Database and as a result, we can see a peak for data being ingressed and egressed in our **Data In** and **Data Out** charts.

![Select a free app service](images/HOL1/18_datainout.PNG)

### **Test our App**

Finally, we test out our App by copying and pasting the URL from the Overview section into a New Tab in our Browser and press **Enter**. 

![Select a free app service](images/HOL1/19_website.PNG)

## Congratulations! 🎊✨🔥 

You've successfully completed this lab by walking through the motions of provisioning Azure resources - an Azure Web App hosting a Wordpress website and a managed Azure SQL Database.

### **Delete Resource Group**

Since we've completed the exercise, it's best practice to delete our resources within our Resource Group. We have to select all 4 of our manually provisioned resources and then select **Delete**.

![Select a free app service](images/HOL1/20_delete_resources.PNG)
![Select a free app service](images/HOL1/21_delete.PNG)
![Select a free app service](images/HOL1/22_delete.PNG)