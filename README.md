# Min(Mun)
Planning in progress: KSP/cybernetics project to develop a minimal implementation of a control system to take a multistage rocket to a specified Kerbin orbit (main goal one), then to a specified Munar orbit (main goal two), then to a landing in a specified spot on the Mun (main goal three) followed by a return to a specified Kerbin orbit (main goal four), and eventually a safe return (main goal five) plus a possibly powered SpaceX-style Kerbin landing in a prespecified location (main goal six).

First stages \(pun intended\):
 - Plan and document the required system structure.
 - Launch and safely land the first stage of an orbit-capable launch vehicle ([like, let's say, this one](http://www.curse.com/shareables/kerbal/241246-realistic-space-x-dragon-dragon-v2-and-falcon)) on Kerbin under power. No chutes. Preferably before somebody else (hopefully) does the same in March/April. The old airfield is a likely target for this operation, seeing as it is vaguely in the right direction and distance for a launch to an equatorial orbit. The difficult bit here will be the stuff required for actually landing in the right place reliably; keeping the rocket pointed down and at a low enough speed is relatively trivial (and already tested). A barge landing is probably a bit optimistic, as it is another part of the system that probably will fail despite being a relatively simple system to control from a cybernetics viewpoint (at least compared to an inverted pendulum); I'm more worried about the limitations and complexities of KSP with having to control and maintain two active vessels at once.
   - Note: How aerodynamically stable is the KSP version for low/medium flight speeds? Are the [speed brakes|control surfaces] at the top realistic/sufficient for the task? 
 - Start working on next level requirements for the upper stages, as outlined below.

Obvious requirements:
- PID-based regulator system object for spacecraft control in different stages of flight and for different spacecraft configurations. Has to dynamically adjust for changes in spacecraft configuration (fuel load, available actuators), and is probably the most difficult part to implement. Attempt to keep it as simple as possible.
- Spacecraft internal finite state machine for control in different stages of flight
  - This is the fun part!
- Lots of calculus - probably of the numeric kind - for approximating the required control inputs and timings, particularly for the Mun <-> Kerbin transfer orbits. Note that a lot of simplification can be done by allowing the system to time accelerate until Kerbin, the Mun and the spacecraft is in a well-defined, simple state where a solution is readily available. There are plenty of tricks and simplifications that KSP players already use for not having to think too hard about orbital maneuvers that the system can implement as well as long they're not too expensive for the craft's (known) delta V budget.
- Telemachus or a similar plugin for getting data in and out of KSP
- http://forum.kerbalspaceprogram.com/index.php?/topic/72605-105-flight-manager-for-reusable-stages-fmrs-v1001/
- Progress videos now that you've got something powerful enough to record video on.
