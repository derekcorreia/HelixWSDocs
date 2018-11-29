# Exercise 3

In this exercise we create the data model for the Events feature module and wire it up to the pages in the website.

## Working with feature templates

1. In Sitecore:
    1. Create a template named "_Event" under "/Sitecore/Templates/Feature/Events"
    1. Add the following fields in a group named "Event": 
        * Title: single-line text
        * Description: rich text
        * Date: datetime
    1. Add the following fields in a group named "Venue":
        * Venue: single-line text
        * Venue Address: multi-line text
    1. Add default values
        * Set the Default Value of the Title field to "$name".
2. In Visual Studio feature project:
    1. Create a new class, "Templates.cs", in the root of the feature module (Feature/Events/Sitecore.Feature.Events)
    1. Add the template and field constants. [See this file](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/events/src/Feature/Events/code/Templates.cs)
    1. Update the IDs in the Templates.cs file to match the ID's of your template and fields.
3. Under /templates in Sitecore:
    1. Create a new "Event" page type template under "/sitecore/templates/project/group/page types"
        * Add the following base templates
            * templates/feature/events/_Event
            * templates/feature/metadata/_PageMetadata
            * templates/feature/social/_OpenGraph
            * templates/foundation/assets/_PageAssets
            * templates/foundation/indexing/_IndexedItem
        * Set the icon to "Applications/32x32/history.png"
    2. Create a "Event List" page type template by duplicating the "News List Page Type"
        * Add the following base templates
            * templates/feature/metadata/_PageMetadata
            * templates/feature/navigation/_Navigable
            * templates/feature/pagecontent/_HasPageContent
            * templates/feature/social/_OpenGraph
            * templates/foundation/assets/_PageAssets
            * templates/foundation/indexing/_IndexedItem
        * Set the icon to "Applications/32x32/folder_time.png"
        * Add default values
            * Configure insert options on Event List's Standard Values and add the "Event" page type
    3. Configure insert options on standard values on the "Home" template
        * Add the "Event List" to the insert options
3. Under /content in Sitecore
    1. Create a new page "Events" under the home page for the group site
        * Use the "Event List" template
        * Make sure the Title and Navigation Title fields are populated with "Events"
    2. Create some test events under the newly created event list page
4. Serialize your changes by running the Sync Unicorn task in Task Runner Explorer