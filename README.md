# Sui-Move-Notes
Programming notes and code snippets regarding the Sui Move programming language. Created by PhD candidate Antonios Giatzis (agiatzis@uom.edu.gr) and Professor Christos K. Georgiadis (geor@uom.edu.gr).

## Basic Knowledge
Unlike other programming languages that are used to code smart contracts, Sui Move control each operation inside the network by the usage of "objects", both for the inputs and the outputs.
For creating a basic code structure, we need to use the `struct` keyword:
```Sui Move
struct Exercises {
    deadlift: u8,
    squat: u8,
    bench press: u8,
}
```
By using the above code, we are able to define:

1) a structure (struct) with the name `Exercises`,

2) with is filled with 3 fields: `deadlift`, `squat` and `bench press`,

3) and each field is a `u8` type (unsigned 8-bit integer that can range from 0 to 255) as a simple example of an athlete who wish to store performance metrics for three exercises: deadlift, squat, and bench press, using 8-bit unsigned integers for each metric-exercise.

Within the above basic code structure, we can add the key or `has key` ability, and a globally unique `id: UID` field in order to create an instance of a Sui object, stored inside the global storage:

```Sui Move
use sui::object::{UID};

struct ExercisesObject has key {
    deadlift: u8,
    squat: u8,
    bench press: u8,
}
```
