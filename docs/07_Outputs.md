---
title: Model outputs
nav_order: 7
---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Outputs

PathFinder generates outputs of different kinds. The main output is the candidates route geometry. Those are generated as ESRI Shapefiles at the case directory, located in the "**routes**" folder. There, the user will find a folder for each candidate, called "**candidate_{N}.shp**", that contains its routes. The line created by the basic routing will be available by the file "optroute.shp". If the user chooses to use any kind of line enhancement, the new line will be available on the same folder, by the name "**optroute_{name of enhancement method choosen}.shp**". 

There will also be a CSV file compiling information of every candidate route result. That file is called "**opt_candidates.csv**" and is located at the "**results**" folder. Its columns are:
* **Route length (km) [`Float`]:** The basic route length.
* **Line enhancement (km) [`String`]:** The enhancement method applied.
* **Enhanced route length (km) [`Float`]:** The enhanced route length. Will be the same as the basic if no enhancement is applied.

If the Tower Arrangement module is used, there will be two additional columns:
* **Tower arrangement (km) [`integer`]:** The choosen tower arrangement code.
* **Total cost (M$) [`Float`]:** The total cost of implementating the line for the choosen arrangement.