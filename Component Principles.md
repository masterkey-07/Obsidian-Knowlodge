# Past

In the past, it was complicated to treat software as "blocks" or "plugins", but now this is something that is possible and standard to do.

# Cohesion - Principles of Composition of Modules and Classes

- **THE REUSE/RELEASE EQUIVALENCE PRINCIPLE**
	- **Acronym: **REP
	- **Definition: ** Projects whose versions accompany each other and that "make sense" to be together, therefore, make sense to be released together
	- **Problem**: "Makes Sense", is not a good measure to define.
	- **Tip: **: _The reuse granule is the liberation granule._
- **THE PRINCIPLE OF COMMON CLOSURE**
	- **Acronym: **CCP
	- **Definition: ** The "Single Responsibility Principle" of Components, to which every component should do one thing. Therefore, the classes that change for the same reason, so when changes are necessary, affect few classes.
	- **Tip: ** _Gather those things that change at the same time and for the same reasons. Separate things that change at different times or for different reasons._
- **THE COMMON PRINCIPLE OF REUSE**
	- **Acronym: **CRP
	- **Definition: ** The "Interface Segregation Principle" of Components, to which every component should depend only on what it uses. Therefore, classes that do not use other classes should not be in the same component.
	- **Tip: ** _Don't force users of a component to depend on things they don't need._


# Component Cohesion Stress Diagram

![[Component Principles 2023-10-03 13.26.17.excalidraw|100%]]


## Component Coupling


 **Problem**: What I did politely because of a dependency that changed.

 **Solution**: Eliminating Structures with Dependency Cycles

 **Dependency Cycles**: Component A that depends on a Component B that indirectly depends on Component A

 **Breaking Cycles**: Applying the "Principle of Dependency Inversion", therefore, Creating Interfaces.


![[Component Principles 2023-10-03 13.28.10.excalidraw|center]]

# Conclusions on Project Design

"Top-Down Design" should not be done at the beginning of the project, as the project's architecture emerges as it grows.
The Design Goal is not for the Functionality of the Application but rather its "Maintainability" and its "Buildability". When starting a project, there is nothing to maintain or build.

As the application grows we focus on reusing components.


# Stable Dependencies Principle

**Definition:** we ensure that modules that are intended to be simple to change do not depend on modules that are more difficult to change, so they will also be difficult to change.

**Stability: ** A module that several modules depend on, therefore difficult to change without causing problems.

**Tip: ** Unstable components must depend on resulting components.


# The Principle of Stable Abstractions

**Goals**: Be Stable and Flexible

**Tip** :
- _A component must be as abstract as it is stable._
- _Dependencies run towards abstraction._

![[Component Principles 2023-10-03 13.29.27.excalidraw|center]]

# Exclusion Zones

## Very Concrete and Very Stable

**Example**: Bank Schema, volatile and with many dependencies, so a big headache when changing.

## Very Abstract and Not Stable

**Example**: Never Used Interface, very abstract but with no one depending on it.

**Then:** the conformity of a project to a dependency and abstraction pattern that is considered a “good” pattern.