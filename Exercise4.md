# Exercise 4

In this exercise, we will create the renderings to show the feature content and configure the overall page layouts for the new page types.

## Configuring Renderings for feature modules

1. In the feature module project in Visual Studio 
    1. Add or validate the following references in the project: 
        * Sitecore.Kernel (referenced via NuGet)
        * Sitecore.Mvc (referenced via NuGet)
        * Sitecore.Foundation.Dictionary (available in the /lib folder of your Sitecore.Demo.Group folder)
        * Sitecore.Foundation.SitecoreExtensions (available in the /lib folder of your Sitecore.Demo.Group folder)
        * Sitecore.Foundation.Alerts (available in the /lib folder of your Sitecore.Demo.Group folder)
    2. Under /Views/Events, create following razor views:
        * EventContent.cshtml - [See content](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/events/src/Feature/Events/code/Views/Events/EventContent.cshtml)
        * Venue.cshtml - [See content](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/events/src/Feature/Events/code/Views/Events/Venue.cshtml)
        * EventList.cshtml - [See content](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/events/src/Feature/Events/code/Views/Events/EventList.cshtml)
    3. Publish the project to the website
2. Under /layout in Sitecore 
    1. Create the following view renderings under **`/sitecore/layout/renderings/feature/events`**
        * Event Content
            * Set the Path to **`/views/events/eventcontent.cshtml`**
        * Venue
            * Set the Path to **`/views/events/venue.cshtml`**
        * Event List
            * Set the Path to **`/views/events/eventlist.cshtml`**
3. In Sitecore, under **`/sitecore/templates/project/group/Page Types`**
    1. Open the presentation details of the Standard Values for the "Article" page type
        * Click "Copy To" on the shared layout for the default device
        * Select the "Event" page type as the target - (Create Standard Values for "Event" if it doesn't exists).
    1. Open the presentation details for the "Event" page type's Standard Values
        * Remove the following renderings:
            * Page Image Header 
            * Page Title
            * Page Body
        * Add the following renderings:
            * **`renderings/feature/Events/Event Content`** (placeholder: **`/page-layout/section/col-wide-1`**)
            * **`renderings/feature/Events/Venue`** (placeholder: **`/page-layout/section/col-narrow-1`**)
    1. Open the presentation details of the Standard Values for the "News List" page type
        * Click "Copy To" on the shared layout for the default device
        * Select the "Event List" page type as the target
    2. Modify the Event List presentation
        * Remove the following renderings from Event List's Standard Values:
            * News List
        * Add the following renderings:
            * **`renderings/feature/Events/Event List`** (placeholder: col-huge)
3. Open the group website and navigate to the "Events" page in the top menu
