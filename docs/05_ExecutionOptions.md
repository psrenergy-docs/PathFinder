---
layout: default
title: Execution Options
nav_order: 5
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# Executions options

PathFinder offers a few execution options that affect the routing or its post processing. The **Routing method** refers to the routing, and **Line enhancement** to the post process.

The Routing Method options are "Traditional" or "Smoothed". The **"Traditional"** option will yield a classic linear Dijkstra routing. Meanwhile, **"Smoothed"** will run a non-linear routing (AqDijkstra) that will avoid sharp turns. The routing is pixel based, that is, the step choice will be made at every pixel of the candidate map. Depending on the map resolution (usually 30x30m), the amount of edges of the result may be exaggerated, that's why it's interesting to use post process methods to enhance that product.

After the routing is completed, three kinds of post processing may be applied to the line to make it more realistic as an electrical power one. The first is **"Simplified"**,  it applies the Ramer-Douglas-Peucker method to make the lines smoother. The second is **"Vertex selection"**, that creates a new graph based on the existing line, checking the possibility of skipping vertexes as to make its number decrease and avoid sharp turns. To do so, the model will run the non-linear AqDijkstra over the new graph. The idea of this model is to make the number and position of the vertexes closer to that of a real power line, that have one vertex per electrical tower and a reasonable distance between them. The last option is **"Tower sitting"**, this method starts by running vertex selection and working over its results. It will make minor ajustments to the vertex positions by considering mechanical constraints of choosen towers to that locations.