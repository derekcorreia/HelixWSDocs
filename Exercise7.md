# Exercise 7

In this exercise we will investigate how to set up a new theme for a project module, how to change the theming context and how to attach the new theme to the site.

## Adding an new design theme

1. Create a new theme css
    1. In Visual Studio open the **`Sitecore.Demo.Group`** solution
    1. In the Visual Studio Task Runner, run the "Auto-Publish-Css" task
    1. Add a "SCSS Style Sheet (SASS)" called "Sweden" to **`/Project/Sitecore.Demo.Group/styles`**
    1. Right click the `Sweden.scss` file and compile it using the Visual Studio Web Compiler
    1. Notice how the Visual Studio Task Runner has published the css file to the website
1. Create the Sitecore theme
    1. In Sitecore under **`/sitecore/system/settings/project/themes/group`** create a new Theme "Sweden"
    1. In the field "Css Assets" enter the value: **`/styles/sweden.min.css`**
1. Change the theme context
    1. Open the template **`/sitecore/templates/project/group/page types/home`**
    1. In the Base Templates field add the template **`/sitecore/templates/foundation/assets/_HasTheme`**
    1. Go to **`/sitecore/content/group/Sweden`**
    1. On the Sweedish Language Version of the item, change the Theme field to "Sweden"
1. Override the stylesheet
    1. In Visual Studio create a new folder **`/Project/Sitecore.Demo.Group/styles/Sweden`**
    1. In this folder create the files (see link for example content):
        * [_fonts.scss](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/multi-site/src/Project/Group/code/styles/sweden/_fonts.scss)
        * [_overrides.scss](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/multi-site/src/Project/Group/code/styles/sweden/_overrides.scss)
        * [_variables.scss](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/multi-site/src/Project/Group/code/styles/sweden/_variables.scss)
    1. Import the files into the **`Sweden.scss`** file
        * [sweden.scss](https://github.com/Sitecore/Sitecore.Demo.Group/blob/feature/multi-site/src/Project/Group/code/styles/sweden.scss)
    2. Reload the sweden.dev.local site and see the new visual theme
