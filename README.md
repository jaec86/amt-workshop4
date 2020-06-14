## Verlet Integration Motion

Verlet integration is a numerical method used to integrate Newton’s equations of motion and it is frequently used to calculate trajectories of particles in molecular dynamics simulations and video games. A Verlet system is formed by a group of points connected to each other by some constraints.

The goal of this project is to build a mesh of connected points and apply Verlet physics to it in order to interact with the cursor on realtime. Also the constraints can be cut if enough force is applied or right click or drag is detected. As mentioned before the Verlet system has two main components, points and constraints, which are the main classes of this script.

The point class stores an array of constraints attached to it and the current and old position so it can calculate the velocity during an update event. Once the velocity is calculated some friction is applied so the point won’t move for eternity. Finally before the update event finishes the old position is stored including velocity and gravity.

The constraint class stores the two points it connects and its length. During an update event the distance between the two points is calculated and is compared with its length. If the distance is less than the length the constraint remains unchanged. If the distance is too big the points are released from the constraint. The points are also released if a right click or drag is detected over the constraint.

A new cloth class is included which represents the mesh with all the points and constraints. Its constructor will build the mesh based on the points and the width of the screen to calculate the spacing between points and initial position.

[DEMO](https://jaec86.github.io/amt-workshop4/)