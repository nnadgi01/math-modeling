**Mathematical Modeling Contest 2022 (MCM)**
==
We use a rider’s power curve to minimize the amount of time the rider takes to cover a set distance.

We split the course into a series of vectors with a set length and defined functions:
1. A continuous function for the rider’s fatigue, that uses recovery and fatigue constants to reduce the amount of force the rider can exert during the current distance segment
based on the forces in the previous segments. From this, we defined a constraint on the rider’s level of
fatigue at each distance segment.
2. Another function that, given the velocity of the previous distance segment, outputs the velocity at the current distance segment. This function considers four primary forces that the rider must overcome to exert force: air resistance, gravitational force, rolling resistance, and kinetic energy. It also uses the mass and surface area of the rider, the velocity of the wind, the grade of the incline, the radius of the rider’s turn, and the previous velocity of the rider.

We used the sine of the road angle to the horizontal for the incline and bounded the rider’s velocity during a turn by the radius of the turn, the gravitational constant, and the friction coefficient.

Our algorithm uses a recursive depth-first search (DFS) approach to output the optimal force at each time segment that maximizes average velocity given a set of constraints. 
