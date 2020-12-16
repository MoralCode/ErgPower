---
category: meeting
---
# Dec 10 2020 Meeting Summary

**Meeting goal:** to sync up regarding the idea/vision for this project and the plans for carrying it out. and also discuss specific challenges i'm likely going to encounter

**Notes taken and organized by:** Adrian Edwards

**Other Meeting Participants:** Ben Clements


## Overall project goal
- Sync up about the goal for the project is
	- Idea from Ben: use this project as a way to improve upon the erging experience/feel and make it more water-like
    	- if we are able to vary the resistance using this system, we could make virtual racing way better. Just think about how an eight feels "easier" i.e. more boat run when everyone is pulling hard. if you could connect 8 ergs with these custom flywheels together, you could use data from all of them to adjust the resistance so if everyone is pulling hard, everyone feels more "boat run". This could possibly also work for cool stuff like racing with someone elses saved workout, racing "with yourself" sorta like two of you in a boat together (isnt this how weighted 2k is calculated?)
	- My original thoughts were just to use it as a way to (in order):
		1. generate a usable amount of green power from an erg
		2. make the resistance from the motor match the level of drag due to air resistance so that it can be used with a very similar if not identical feel to a normal erg
		3. see if its possible to make it a commercial product


## Driving the motor
There seem to be two major ideas on this topic:

1. Ben's idea to use an electronic speed controller (ESC) to generate the appropriate PWM for driving the motor so that it can be driven as a way to apply a force to the flywheel as resistance
	- ESC’s for larger motors are often more expensive than the motor itself
	- do electronic speed controllers work if fed 3 phase power as input?
	- If we did this we would need to hook both the thing that's going to be using the power, which would mean the ESC would just be directly powering the thing that we are trying to power

![Diagram illustrating the problem of connecting both ESC and load to the generator at once](../files/meetings.ESCproblem.png)


2. My original plan of applying resistance by controlling current draw.
	- similar to those pedal-powered exhibits in museums that let you power different things (energy efficient lights, incandecent lights, electric heater, etc.) with pedal power to let you feel how much energy each of them takes
	- need a way to (ideally digitally) regulate the power draw on the generator which i feel is possible but im not certain that it exists


We should ask an EE which of these ways is better to use.



## Data and Measurements

it is going to be very important/interesting to have access to stroke for stroke data from the erg monitor
 - the concept2 SDK should already allow this as the ErgData app is able to update every stroke.

Improving upon the concept2 erg's drag profile is gonna require a **lot** of data

is there a meaningful amount of energy even in the flywheel?

measuring intertia of flywheel could be important.

Essentially we need to understand how flywheel works from a physics standpoint so we are able to keep it the same and/or make it closer to water-like resistance

**Ways to measure flywheel Speed:**
 - electrical contacts touching the flywheel and bridging once per rotation
 - optical tachometer
 - 

ideally we want to sample once per rotation of the flywheel by logging the time at each rotation.


### force curves

the force curve is very important and could be super helpful in helping match the current air-resistance-based force curve with the generator-driven one.

we can use it to create a profile for the energy in the flywheel. essentially creating a model for the force inputs and outputs for the flywheel. i.e. “if at X split and put in Y joules of work, RPM go up by Z”

the integral of (AKA area under) the force curve is the total force put in

![sample force curve graph of force over time with the integral shaded](./forcecurve-integral.png)

can you get force curve data from the concept2 SDK? how about directly from the monitoror cable attached to it?


### flywheel
what are the specs of the cable/sensor already attached to the flywheel? is this usable?

whats the relationship between force in and RPM output

Rotational intertia – newtons second law – sum of moments of inertia = I \* ? (didnt catch the whole formula)

there are two unknowns in this formula: moment of intertia and force/torque from air resistance. can only solve for one unknown at a time

*moment of intertia* is a measure of how (rotational/radial density)

units are probably something like kg m/s^2??

Would need to 3D model a flywheel in SolidWorks to accurately model the moment of inertia (and possibly also simulate air resistance as the equations are much more complicated than the standard simple object in static air omes).


## Energy Conversion

The energy that comes out of the BLDC (Brushless motor) is going to be 3-phase AC. 

For charging phones and other small projects, this will need to be DC
 - We could use a 3-phase rectifier like the one in the electroboom video about 3-phase AC, the comparison of motor types as generators, or the 3-phase rectifier from the Green MicroGym Kit

However, if this energy is going to be fed back into a household power grid, it's going to need to be AC.

Converting from AC to DC and back AC again is probably gonna add a ton of inefficiency.

might need to use some energy to run the motor as well (for providing resistance). See [Driving the motor](#Drivingthemotor) section.



# Next Steps/Action Items
 - Research the capabilities of the Concept2 SDK and figure out what data we can get out of an erg
 - Get an erg flywheel to take measurements on and make a 3D Model 
 - Find/reach out to an EE to ask which of the ways to drive the motor is best
