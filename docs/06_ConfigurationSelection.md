## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Tower arrangement selection

Once the routing of a candidate is complete, PathFinder offers a feature module to create a basic budget and engineering for that power line. The result is based on a choice of a pre existing configuration from a database of options. This module has its own special elements to define the engineering possibilities, those are **Cables**, **Towers** and **Tower Arrangements**. A Tower Arrangement is defined by the choice of a Cable and a Tower. This combination will yield particular electrical parameters and constraints. PathFinder will choose the configuration of minimum loss considering an adequate power flow gap according to the candidate's electrical requirements.

The parameters of each element that compose the database is detailed as follows. As previously, each element must have a unique name and identification code.

## Parameters

### Cables
* **Internal radius (mm) [`Float`]:** The internal radius of the conductor.
* **External radius (mm) [`Float`]:** The external radius of the conductor.
* **Cross-section (MCM) [`Float`]:** The conductor's cross-section area, on MCM (or kcmil, thousands of circular mils).
* **Nominal ampacity (A) [`Float`]:** The current value that flows in the conductor on nominal conditions.
* **Emergency ampacity (A) [`Float`]:** The current value that flows in the conductor on emergency conditions.
* **Resistence at 25<sup>o</sup> (Ohms) [`Float`]:** The cable electrical resistance at 25<sup>o</sup> Celcius.
* **Resistence at 50<sup>o</sup> (Ohms) [`Float`]:** The cable electrical resistance at 50<sup>o</sup> Celcius.

### Tower
* **Voltage level (kV) [`Float`]:** The tower's nominal voltage level.
* **Geometry [`String`]:** The geometrical alignment of the phase cables.
* **Circuits [`String`]:** If the tower has simple or double circuits.
* **Distance A to B (m) [`Float`]:** The distance between the A and B phase cables.
* **Distance B to C (m) [`Float`]:** The distance between the B and C phase cables.
* **Distance A to C (m) [`Float`]:** The distance between the A and C phase cables.
* **Distance between circuits (m) [`Float`]:** The distance between the tower circuits. Has value "0" if it's simple.

### Tower Arrangement
* **Tower [`string`]:** Which tower the arrangement uses.
* **Cable [`string`]:** Which cable the arrangement uses.
* **Number of conductors [`integer`]:** How many cables there are at each phase beam.
* **Resistance (Ohms/km) [`float`]:** The steady-state direct sequence equivalent electrical resistance per kilometer.
* **Reactance (Ohms/km) [`float`]:** The steady-state direct sequence equivalent electrical reactance per kilometer.
* **Susceptance (S/km) [`float`]:** The steady-state direct sequence equivalent electrical susceptance per kilometer.
* **Unit price (k$/km) [`float`]:** The monetary cost of implementating the Tower Arrangement per kilometer.
