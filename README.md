# Min(Mun)
Planning in progress: KSP/cybernetics project to develop a minimal implementation of a control system to take a multistage rocket to a specified Kerbin orbit (main goal one), then to a specified Munar orbit (main goal two), then to a landing in a specified spot on the Mun (main goal three) followed by a return to a specified Kerbin orbit (main goal four), and eventually a safe return (main goal five) plus a possibly powered SpaceX-style Kerbin landing in a prespecified location (main goal six).

Obvious requirements:
- PID-based regulator system object for spacecraft control in different stages of flight and for different spacecraft configurations. Has to dynamically adjust for changes in spacecraft configuration (fuel load, available actuators), and is probably the most difficult part to implement. Attempt to keep it as simple as possible.
- Spacecraft internal finite state machine for control in different stages of flight
  - This is the fun part!
- Lots of calculus - probably of the numeric kind - for approximating the required control inputs and timings, particularly for the Mun <-> Kerbin transfer orbits. Note that a lot of simplification can be done by allowing the system to time accelerate until Kerbin, the Mun and the spacecraft is in a well-defined, simple state where a solution is readily available. There are plenty of tricks and simplification that KSP players already use for not having to think too hard about orbital maneuvers that the system can implement as well as long they're not too expensive for the craft's (known) delta V budget.
- Telemachus or a similar plugin for getting data in and out of KSP
