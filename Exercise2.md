# Exercise 2

In this exercise we hook up the new feature module to work with items in Sitecore. We'll work in Content Editor to create some scaffolding folders for our new feature, and then use Unicorn to serialize the items out of Sitecore. Serializing the items makes it so we can include them in our solution and source control, and more easily deploy them to other developers and environments.

## Working with Items in Sitecore

1. Log in to your Sitecore instance at group.dev.local. From the launchpad, open the Content Editor.
    1. Create the folder **`/sitecore/templates/Feature/Events`**
    1. Create the folder **`/sitecore/layout/renderings/Feature/Events`**
1. Open the Feature project in Visual Studio 
    1. To the App_Config/Include/Feature folder, add a new file "Feature.Events.Serialization.config"
    2. Add the Unicorn configuration to the file. [See this file](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/events/src/Feature/Events/code/App_Config/Include/Feature/Sitecore.Feature.Events.Serialization.config)
    3. Save the solution and all files in Visual Studio. Then, publish the Unicorn configuration using either Visual Studio or Gulp.
1. Serialize the items through Unicorn
    1. Open http://group.dev.local/unicorn.aspx
    2. Find the "Feature.Events" configuration and press the "Reserialize" button. You may need to perform an initial serialization for "Feature.Events" if the reserialize button is not visible. This will be at the bottom of the "Feature.Events" section.
