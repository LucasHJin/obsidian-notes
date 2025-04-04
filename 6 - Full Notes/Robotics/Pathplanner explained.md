2025-01-12 20:52

Status:


Tags:
[[cs]] 
[[robotics]]


___________________________________________________________________________
# Pathplanner explained

**What?** 
- Simplified way of creating autos (plan paths + event markers and then create autos)

**Paths:** one continuous motion from some start point to an end point
- Only one part of auto
**Waypoints:** define how the path looks like
- **Anchor point:** goes through exact point
- **Control point:** more general guideline
**Global constraints:** kinematic constraints of the robot along the entire path
- I.e. max velocity, acceleration, etc.
**Ideal starting constraint:** state the robot should start at (i.e. will it already be moving/rotated or start facing straight and unmoving)
**Goal end state:** how it will end (same idea as above)
**Rotation targets:** points where the robot targets (starts a given rotation)
- Looks at next rotation target in target tree and rotates to that
**Event marker:** points along the path where other commands should be triggered while path following
- All commands by EM will end at end of a path
**Constraint zones:** places where you can change the kinematic (global) constraints
**Point towards zones:** create a zone along a path where the robot should aim at a position on the field
**Path optimization:** generates a recommended path
**Autos:** define a complete autonomous routine
- Can be loaded as a full autonomous command in robot code via PathPlannerLib's auto builder functionality
	- Defined as a sequential command group
- **Command group (tree):** define the entire autonomous routine within a sequential command group





# References
https://pathplanner.dev/gui-getting-started.html 
