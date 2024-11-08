# Instruction
Load the page and the animation will appear.

# Method
This prototype uses the time-based method to animate the artwork.

# Animation Details and Technical Explanation
## Iteration 1
Based on the group code, I removed the `noLoop()` function in the setup block to animate the entire artwork. To control the speed of animation of each element, I introduced the frameCount variable to the `display()` method in the `Circle` class and to the `drawTree()` function.

## Iteration 2
This iteration further develops the animation technique in Iteration 1 in two aspects: the **Tree** and the **River**.

For the Tree, my aim is to depict an imagery of growing and falling leaves. To achieve such effect, I introduced a new array called `leaves`, a new variable called `maxLeaves`, and `Leaf` class. The `leaves` array stores `Leaf` objects generated from the new for loop in the `drawTreeCircles()` function. The loops repeats until the number of `Leaf` objects in the `leaves` array reaches `maxLeaves`. In the Draw section, I also added  `leaves = leaves.filter(leaf => leaf.y < height);` to remove any `Leaf` object that has fallen off the canvas from the `leaves` array to make room for additional objects.

For the River, the goal is to produce a wave effect by rotating the spiral line inside the outer circle. This rotating efffect is triggered by a new `rotation` variable that changes over time at the randomized speed of `rotationSpeed` introduced to the Circle class.

In addition to the animation effects, I modified the colors of the Grass to become darker, as it was competing with the other foreground elements.

## Iteration 3
In the final iteration, I wanted to add some fish that jump above the river and go back into the river. To create this animation, I modified the `Circle` class to incorporate new parameters and methods. Firstly, I defined new properties, `fishJumpHeight`, `fishJumping`, `fishDirection` and `fishX`, in the constructor function of the Circle class (refer to the comments in sketch.js file for the definition of each property). Then, I created a new method `drawFish()` to specify the shape of the fish as well as to define how the fish should jump up and fall back down into the river. Lastly,the new properties and method are implemented in the `display()` method to determine the logic of when to trigger the fish jump.
