# Javascript Projects

## Project 1 - Build a Martian Robot

This JavaScript project involves building a virtual automaton, a little program that performs a task in a virtual martian world. Our automaton will be a space robot picking up and dropping off important cargo.

Note: This project involves using an object for persistent data, understanding graphs and writing a simple pathfinding program that traces the points that the robot will visit, the points where there is a drop-off and the points where there is a pick-up. At any given time, the robot will only know about two things - it's current position or point in the graph, and the cargo it currently holds. The task is described below briefly.

Please Note: Object Oriented Programming is a bad approach to solving this project. In the sections prior to the project, we will explain why. But students are asked to think and solve for themselves. We will also provide text hints in our AcademyJS notes.

## The Task

Our robot will be moving around Mars. There are parcels in various places, each addressed to some other place. The robot picks up parcels when it comes to them and delivers them when it arrives at their destinations.

The automaton must decide, at each point, where to go next. It has finished its task when all parcels have been delivered. To be able to simulate this process, we must define a virtual world that can describe it. This model tells us where the robot is and where the parcels are. When the robot has decided to move somewhere, we need to update the model
to reflect the new situation.

You are also required to write a `move` method. The move method is where the action happens. It first checks whether there is a road going from the current place to the destination, and if not, it returns
the old state since this is not a valid move. Then it creates a new state with the destination as the robot’s new place. But it also needs to create a new set of parcels—parcels that the robot is carrying
(that are at the robot’s current place) need to be moved along to the new place. More details regarding how to go about this project will be provided in the class.

---
## Project 2 - Build a Vampire Logger

The Vampire Logger project will strengthen the following concepts for students:

1. Mutability
2. Array Loops
3. Array Methods
4. Object Methods
5. Mathematical Computation in large data sets.

The tast requires to store a data set in an immutable way, and then applying mathematical operations on it to find correlation and other statistical measures.

### The Task:

Every now and then, usually between 8 p.m. and 10 p.m, Samuel finds himself transforming into a Vampire.

On one hand, Samuel is quite glad that he doesn’t have classic blood-sucking vampire syndrome. That would be a real problem!

Instead of having to worry about accidentally eating the neighbor (that would be awkward), he worries about being burnt by bright light (Vampires cannot stand light). 

Now Samuel would prefer to get rid of his condition entirely. The irregular occurrences of the transformation make him suspect that they might be triggered by something. 

For a while, he believed that it happened only on days when he had been near people wearing red clothes. But
avoiding people wearing red clothes did not stop the problem.

Switching to a more scientific approach, Samuel has started keeping a daily log of everything he does on a given day and whether he changed form. With this data he hopes to narrow down the conditions that trigger the transformations.

The first thing he needs is a data structure to store this information. This is your task. Once you have figured that out, you need to use mathematical operations to find Pearson's Correlation Coefficient between any task and transforming into a vampire. Then you have to find the two tasks, that when done together, cause the transformation.More details regarding how to go about this project will be provided in the class.
