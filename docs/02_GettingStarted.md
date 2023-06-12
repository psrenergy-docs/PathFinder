---
layout: default
title: Getting Started
nav_order: 2
---

# Getting started with PathFinder

On this section will be shown an example application of PathFinder. It'll be a simple example, more details about parameters and features are availble on the next sections. In this case, a single candidate will be created to connect two buses. The buses locations can be seen on the corner map, according to the coordinates at the data tab.

![](/assets/gs_buses.png "Buses tab")

We'd like the route to avoid crossing urban areas and forests, so those geometries will be added as spatial constraints. As we are very concerned about the environment, we'll make the reference cost of crossing it more expensive than the one of urban areas, and add a greater buffer as well. 

![](/assets/gs_spac_const.png "Spatial constraints tab")

Then, let's define our candidate by setting the two buses we want to connect, pointing to our desired spatial constraints and our slope map.

![](/assets/gs_cand.png "Candidates tab")

Now, we can already generate a route by pressing "Run PathFinder" on the "Run" tab.

![](/assets/gs_run.png "Run tab")

The result will be available on "routes/optroute/candidate_1/optroute.shp", let's check it out.

![](/assets/gs_route.png "Route tab")

Looks good! The route considers the terrain and avoids the constrained areas.
