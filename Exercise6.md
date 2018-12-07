# Exercise 6

In this exercise, we will add an additional site to the solution to support a complex multi-site and multi-language scenario.

## Adding an additional site

1. In Sitecore, under **`/system/Languages`**
   * Create new language: *Swedish (Sweden): Svenska (Sverige)*: `sv-SE`
1. Switch to Swedish in the Language selector in Sitecore
1. Move to **`/Sitecore/Content/Group`**
    1. Create new Home page "Sweden" under **`/Sitecore/Content/Group`**
        - Update the fields with [Swedish text](http://xn--lkss-soa3h.vogelius.se/) (or use some [Lorem Ipsum](https://www.lipsum.com/) so you can identify the new version.)
    1. Verify that the site is visible on http://group.dev.local/sv-SE/Sweden
1. Add Swedish version to **`/Sitecore/Content/Group`**
    1. Update fields, ensuring a theme is selected.
    1. Verify that the site is ok on http://group.dev.local/sv-SE/Sweden
1. Setup Site definition and IIS binding
    1. Modify your hosts file to add the domain: **`sweden.dev.local`**
    1. Add a new IIS binding to the habitat.dev.local site: **`sweden.dev.local`**
    1. Add <site> to **`/App_Config/Include/Project/Sitecore.Demo.Group.config`** in the Sitecore.Demo.Group project.
        - duplicate the `<site name='group'>` node
        - set `name="sweden"`
        - set `targetHostName="sweden.$(rootHostName)"`
        - set `startItem="/Sweden"`
        - set `hostName="sweden"`
        - set `language="sv-SE"`
    1. Add `<site>` to **`/App_Config/Include/Project/z.Sitecore.Demo.Group.DevSettings.config`** in the Sitecore.Demo.Group project.
        - duplicate the `<site name='group'>` section
        - set `name="sweden"`
    1. Run the default gulp task to rebuild and publish your changes.
    1. Verify that the site is visible on http://sweden.dev.local
        * Use the Site menu to navigate between the Swedish and English site
1. Create Swedish Dictionary texts
    1. Locate the **`/sitecore/content/group/global/dictionary`**
    1. Add the following to `<site name='sweden'>` in **`/App_Config/Include/Project/z.Sitecore.Demo.Group.DevSettings.config`**
        * `<patch:attribute name="dictionaryAutoCreate">true</patch:attribute>`
    1. Publish the z.Sitecore.Demo.Group.DevSettings.config file using gulp or Visual Studio
    1. In a new browser window (either an incognito window, or use a different browser altogether), navigate to http://sweden.dev.local
    1. Switch back to your content editor browser window, and navigate to **`/sitecore/content/group/global/dictionary`** and see that the items are created
        * Navigate to the Dictionary Entries under each Dictionary Folder
        * For each Dictionary Entry, add Swedish text to the Swedish version of the item.
1. Setup Home Page presentation
    1. Copy final layout from **`/Sitecore/Content/Group/Home`** to **`/Sitecore/Content/Group/Sweden`**
        * In Content Editor, turn on Raw Values and Standard Fields from the _View_ tab.
        * Select **`/Sitecore/Content/Group/Home`**, and copy the value from the Layout -> Final Renderings field.
        * Select the **`/Sitecore/Content/Group/Sweden`** item
        * Change the language to Swedish
        * Paste value into the Layout -> Final Renderings field.
        * turn off Raw Values and Standard Fields from the _View_ tab.
    1. Move **`/Sitecore/Content/Group/Home/_Local`** to `Global`
    1. Add Swedish language content to the Teasers in **`/Sitecore/Content/Group/Global/Teasers`**
1. Clone pages to Swedish site
    1. Clone About and Operations from **`/sitecore/content/Group/Home`**
    1. Create Swedish page versions
    1. Change settings on **`/sitecore/content/Group/Settings/Datasources/pageteaser`**
    1. Change datasources on the Operations page
