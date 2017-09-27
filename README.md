## 3D Separating Axis Theorem implementation in Unity

This is a simple implementation of the Separating Axis Theorem (SAT) in Unity.
SAT is an approach to collision detection, based on the principle that if you are able to draw a line between 2 polygons they are not colliding.

![SAT](https://s3.amazonaws.com/irix-github/separatingAxisTest.gif)

**Explaination** 

[http://www.dyn4j.org/2010/01/sat/](http://www.dyn4j.org/2010/01/sat/)

**References** 

Initially I started with this tutorial and Unity code:

[http://thegoldenmule.com/blog/2013/12/supercolliders-in-unity/](http://thegoldenmule.com/blog/2013/12/supercolliders-in-unity/)

However, this didn't pick up all the collisions correctly.

The correct axes were worked out based on this post:

[https://gamedev.stackexchange.com/questions/44500/how-many-and-which-axes-to-use-for-3d-obb-collision-with-sat/](https://gamedev.stackexchange.com/questions/44500/how-many-and-which-axes-to-use-for-3d-obb-collision-with-sat/)


And some optimisations to early out were added if a separating axis is found early in the calculations.

**Useage** 

This is a simple Unity project. Run in the editor and drag the cubes around. When they intersect from movement, rotation or scaling they will turn red.

There is some basic penetration calculation code in there, but it is unreliable. SAT is best used for detection only.
