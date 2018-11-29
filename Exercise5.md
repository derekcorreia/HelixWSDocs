# Exercise 5

In this exercise, we will add the ability to add a map location to an event, which shows how multiple modules can act together to compose functionality.

## Extending the Event Page Type

1. In Sitecore, Open the "Event" page type template under `/sitecore/templates/project/group/page types`:
    1. Add the following base template
        * `templates/feature/maps/_MapPoint`
1. Open the presentation details for the "Event" page type's standard values
    1. Add the following renderings:
        * `renderings/feature/Maps/Map` (placeholder: /page-layout/section/col-narrow-1)
    1. Open the component properties on the Map rendering
        * Set "Zoom Level" to 15
1. In Sitecore, navigate to `/sitecore/content/Group/Home/Events`
    1. Add map points to the test events created in the previous exercises
1. Open the group website and navigate to the "Events" page in the top menu. On the event detail pages, you should now see map renderings of the locations you set.