---
layout: default
title: Element Parameters
nav_order: 4
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# Element Parameters

In this section the parameters of each PathFinder element (Buses, Maps, Spatial Constraints) will be detailed. It is important to understand each one of them to be able to yield and tune reasonable results.

All elements have an `integer` number as an identification **Code**. All codes **must be unique** for each element category. They also have a unique **Name** (`string`).

## Buses
* **Longitude [`Float`]:** The coordinate longitude on EPSG:4326.
* **Latitude [`Float`]:** The coordinate latitude on EPSG:4326.

## Spatial Constraint
* **File Path [`String`]:** The path to the ESRI Shapefile containing the constraint geometry. The path is relative to the case directory.
* **Type [`String`]:** The constraint context, such as "Urban", "Environment", etc.
* **Reference Cost (M$/km) [`String`]:** The additional cost of crossing this area. The higher this value is, the harder the route will try to avoid it.
* **Geometry [`String`]:** The constraint geometry type.
* **Buffer [`Float`]:** The buffer value to apply to the constraint before routing. A geometry buffer is simply to "fatten" the shape, slightly increasing its frontiers. The pratical effect of a buffer is that so the router will avoid getting closer to the restricted area.
* **Inside [`Binary`]:** If the constraint refers to the inside or the outside of the geometry. For example, if there is a geometry that describes the frontier of the country where the routing occurs, and we'd like the router to avoid getting outside the frontier, our constraint refers to the outside of the geometry. Therefore, the Inside parameter should be set to "No".

## Maps
* **File Path [`String`]:** The path to the TIFF file containing the raster map. The path is relative to the case directory.
* **Type [`String`]:** The map type. This parameter indicates the purpose of the map to the model. The most important (and indispensable) one is "Slope", that keeps the declivity of the terrain.

## Candidate
* **Bus from [`String`]:** The bus where the routing will start from.
* **Bus to [`String`]:** The bus where the routing will end.
* **Consider [`Binary`]:** Indicates that this candidate should't be ignored during the routing of candidates.
* **Reference cost (M$/km) [`Binary`]:** Which cost per distance to consider (while crossing constrained areas or not).
* **Reference capacity (MW) [`Float`]:** The maximum electrical power that will flow along this line.
* **Voltage level (kV) [`Float`]:** The nominal line electrical voltage.
* **Spatial Constraints:** The spatial constraints that will be applied to this candidate.
* **Maps:** The maps to apply to this candidate. **Each candidate must have a unique Slope map.**