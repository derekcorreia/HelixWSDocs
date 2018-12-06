# Exercise 1

In this exercise we will create a new feature module in our solution. 

Modules are a conceptual grouping of all assets related to a single business requirement. When working in a Helix solution, you will create modules to contain all of these assets by following the steps we walk through in this exercise, leveraging Visual Studio and File Explorer. 

## Creating a new Feature Module

The following steps are required for creating the Events module in Visual studio:

1. Open Windows File Explorer and navigate to **`c:/projects/sitecore.demo.group`**
    1. Create the following folder structure: **`/src/Feature/Events`**
2. Open Visual Studio 2017
    1. Open the Habitat Group website solution from **`c:/projects/sitecore.demo.group`**
    1. Create a Solution folder in the root named “Feature”
    1.	Create a Solution folder in “Feature” named “Events”
3. Create a new Visual Studio Project in the “Events” folder:
    1. Use the “ASP.NET Web Application” template
    1. Location should be **`C:\Projects\Sitecore.Demo.Group\src\Feature\Events`**
    1. Name should be **`code`** as this will create the correct folder structure. We'll rename the project in the next step.
    1. On the next screen, choose the “Empty” template and check the “MVC folders” checkbox
4. Set the properties for the new project
    1. Rename the project to **`Sitecore.Feature.Events`**
    1. In the project properties set the assembly name and namespace to **`Sitecore.Feature.Events`**
    1. Update the project to .NET Framework 4.7.1
    1. Delete the App_Data, App_Start and Global.asax files and folders
5. Ensure the web.config is not published with the project
    1. Open properties for the web.config and /views/web.config files
    2. Set “Build Action” to “None”
6. Add configuration files
    1. Create the following folder structure under Sitecore.Feature.Events: **`/App_Config/Include/Feature`**.
7. Add Sitecore Kernel NuGet reference
    1. Right-click the project and select "Manage NuGet Packages"
    1. Change package source to the Sitecore NuGet feed (note: you may not need to change the source specifically if you have "All" sources selected)
        1. See https://doc.sitecore.com/developers/91/sitecore-experience-management/en/sitecore-public-nuget-feed-faq.html
    1. Click Browse 
    1. Find and install Sitecore.Kernel, and select version 12.0.0 
    1. Find and install Sitecore.Mvc, and select version 12.0.0
7. Set publish options
    1. Copy the **`/Properties/PublishProfiles`** folder from the Project/Sitecore.Demo.Group project into the same place in the Sitecore.Feature.Events project
8. Publish the project (note -- we're using Gulp in this workshop to do publishing and deployment, not Web Deploy)
    1. Save the Visual Studio solution
    1. In the Task Runner window, run “Publish all Projects”. If Task Runner Explorer isn't visible in your workspace, you can add it by selecting View -> Other Windows -> Task Runner Explorer in Visual Studio.
