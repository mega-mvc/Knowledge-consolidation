# Concepts
"An architecture's ultimate goal is seperation of concerns. 
It divides software into layers and defines how these layers interact with each other"

# Understanding architecture layers 
Simple, comprehensive description: https://www.youtube.com/watch?v=JubdZIdLQ4M&ab_channel=DrawingBoxes

# Dependency rule
Source code dependencies **must goes only inward**, toward higher-level policies.
The center of dependency circle/layer could be the **usecases** (aka what our system does), and this should be the last to change

# Clean diagram for iOS

## Example project
https://medium.com/@ami0275/mvvm-clean-architecture-pattern-in-android-with-use-cases-eff7edc2ef76

## Applied arch diagram 
<img width="1410" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/e88e2908-50de-45a0-9b16-4ec9614f66e1">




