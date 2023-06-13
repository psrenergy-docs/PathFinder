---
layout: default
title: Home
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# Welcome!

This page features documentation about the PathFinder model and interface. PathFinder is a product that aims to automize and simplify the process of creating routes to connect pair of locations of earth. Its development is focused on the yielding of power line candidates for energy grid expansion, but it also offers general features that can be applied on different routing applications.

PathFinder uses Dijkstra based algorithms to optimize the route between two points, making it as shorter, cheaper and realistic as possible. Its user must become familiar with its four main entities: **Buses**, **Candidates**, **Spatial Constraints** and **Maps**. Thoose are the basic classes used to create geographical routes.

On an energy transmission context, a bus is an electrical node where lines may connect and be operated. On the broader scope of PathFinder, **Buses** are simply locations of interest that we might want to connect. If Earth was an empty plane, that'd be pretty easy to accomplish. But in reality, there are several constraints to how a path can be routed, and it's interesting to avoid most thoublesome aeras as possible to yield short and cheap channels. On PathFinder, those constraints are classified between two categories: topological and area constraints.

**Spatial Constraints** aim to describe obstacles better represented as bidimentional polygons, such as lakes, forests or cities. Each Spatial Constraint indicates an area that the user would like to avoid crossing on its routing to a certain degree. PathFinder represents that avoidance will as financial loss, in other words, once the user communicates how much more expensive is the crossing of an area per distance unit, the model will decide if it is worth it to do so and how. The user will input those geometries as ESRI Shapefiles.

Meanwhile, **Maps** are used to represent topological constraints, such as mountains and hills. They describe the 3D terrain where the routing occurs, allowing the model to acquire a more realistic concept of distance and space. The main Map used is a georeferenced TIFF **declivity** file.

Finally, a **Candidate** is defined by a pair of **Buses**, linked to a set of **Spatial Constraints** and a declivity **Map**. With this set of data, PathFinder can optimize a route to connect both locations while considering the given spatial and geometrical constraints. Since the routing will occur over the area the **Map**, it's very important that both buses are cointained in it and that there're no missing data that makes it impossible to connect them.
