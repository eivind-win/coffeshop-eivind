# CoffeeForEveryone

## The coffeeShop case study

In this project we created two websites both located in New York and London. 

The one called, contosocoffeelondon and the other contosocoffeenewyork. 

Difficulty Level 3: Host the Docker Container solution via Azure Container Registries and pull into an Azure ACI solution.

## Company Overview

Contoso Coffee is a small coffee house that is opening soon in London and New York, they are looking for a cloud hosted solution for their website and data storage, costs must be kept to a minimum.

Here is the steps to create the project. 

1. Build a docker image 

2. Run a docker container. 

3. Create a container registry in Azure. 

4. Create two Azure container instances (ACI) that runs the website in both London and New York. It has to be in different regions because.

5. Then loadbalance those two with geo-redundancy. We chose Traffic Manager. Can use Front door as well. 

6. Create a storage account with blob storage and create a lifecycle management rule that says move to Archive tier after 30 days. Here we created a SAS key that can last for x amount of time. 

## User accounts

Contoso coffee requires 3 Administrators for the day to day control of the solution.

*Bob*

Bob will require full admin access as it will be his responsibility to manage and track billing for the Contoso Coffee website and is the owner of Contoso Coffee. He will therefore get global admin and owner role. 

*Dave*

Dave requires admin access to the resources hosted on Azure for the Contoso Coffee website but not overall administration of the Contoso Coffee subscription. He will get contributor role scoped to the resource group. 

*Mark*

Mark will require read-only access to the Contoso Coffee resources. He will therefore get read-only access scoped to the resource group. 

  

<img title="" src="assets/c89edcde4a2933f30543e3de119b3798a3e62829.png" alt="Contoso coffee_users (1).png" data-align="inline">

## Load Balancing and Geo-redundent access

Contoso Coffee will operate in London and New York, because of this a solution will need to be configured that allows the US users to access a more local server than London and vice versa. Load balancing can be achieved through DNS redirection or a geo-load balanced solution.



![ContosoCoffee_Website hosting (3).png](assets/42bd992c105c28ef62999103e03df026410634d4.png)

## Storage

- Storage account V2.
- Have created already.
- Needs blob container. 

Contoso coffee is planning to store a large amount of image information that will be shared with staff members and clients. These images will be scans of 35 and 120 film for hipster photography that will be displayed around the coffee shop. The storage solution should minimize costs by automatically archiving data onto slower storage when required. A SAS key solution should be created for a future image gallery solution to display images on a TV in the Coffee Shop running a small Raspberry Pi solution locally hosting a web page to display the images. Bonus points for creating an image display web app.



![Blank diagram.png](assets/2585d238afb02d3fb31dfe83d72baaeb4d14148c.png)
