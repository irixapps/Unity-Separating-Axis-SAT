## 3D Separating Axis Theorem implementation in Unity

This is a simple implementation of the Separating Axis Theorem (SAT) in Unity.
SAT is an approach to collision detection, based on the principle that if you are able to draw a line between 2 polygons they are not colliding (2D), and in 3D there exists a plane that can seprate 2 convex polygons.

![SAT](https://s3.amazonaws.com/irix-github/separatingAxisTest.gif)

**Explaination** 

[http://www.dyn4j.org/2010/01/sat/](http://www.dyn4j.org/2010/01/sat/)

**References** 

Initially I started with this tutorial and Unity code [http://thegoldenmule.com/blog/2013/12/supercolliders-in-unity/](http://thegoldenmule.com/blog/2013/12/supercolliders-in-unity/)

_However, this didn't pick up all the collisions correctly._

The correct axes were worked out based on this [https://gamedev.stackexchange.com/questions/44500/how-many-and-which-axes-to-use-for-3d-obb-collision-with-sat/](https://gamedev.stackexchange.com/questions/44500/how-many-and-which-axes-to-use-for-3d-obb-collision-with-sat/)

**In 3D for 3 cubes, the following 15 axes are needed**

* 3 axes from object A (face normals)
* 3 axes from object B (face normals)
* 9 axes from all the pairs of edges of A and edges of B (3x3)


The 9 axes are made up of cross products of edges of A and edges of B

* Ae1 x Be1 (Edge 1 of A cross edge 1 of B)
* Ae1 x Be2
* Ae1 x Be3
* Ae2 x Be1
* etc

Some optimisations to early out were added if a separating axis is found early in the calculations.

**Useage** 

This is a simple Unity project. Run in the editor and drag the cubes around. When they intersect from movement, rotation or scaling they will turn red.

There is some basic penetration calculation code in there, but it is unreliable once multiple intersections can be interpreted. SAT is best used for detection only.
