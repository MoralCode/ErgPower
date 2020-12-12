---
layout: default
---

# Overall Project Plan

## Project Goal

- Develop a proof of concept for replacing the flywheel of an Erg flywheel (fundamentally just a device to sink excess energy into air resistance) with a generator as a method of producing green energy that can be used for powering small projects, charging devices, or sending back into the grid to make a small impact on your home's power bill

## Requirements (not specifications)
- To Be Written 

## Approximate Project Phases
Not all of these phases may be taken to completion, but they represent the approximate order and ultimate vision for the project and help organize outstanding questions such that they can be tackled in a reasonable order.

### Phase 0 – Pretotype

- Is this something rowers are interested in?
	
	- Is there interest from the market in people buying this?
	- Is there interest from people to help develop this?
	- Could this be marketed to gyms as an add-on to ergs? A la
		thegreenecogym?

### Phase 1 – Collect Baseline Measurements

- Flywheel
	
	- How much energy does the flywheel have?
		
		- How fast does an erg flywheel spin?
			
			- From the WPI paper: peaks at like 800 RPM (not clear if
				this is absolute max though). RPM ranged from 395 to 780 and angular velocity
			ranged from 41.36 to 81.68 radians per second

			- Use an Optical tachometer and arduino to datalog it
				(maybe there’s a better way and the data can be
				crowdsourced)
		
		- How heavy is the flywheel?
		
		- How much is air resistance affecting the flywheel
		
		- How much torque?
			
			- From WPI paper torque peaked at about 15 NM
		
		- How does the flywheel connect to the axle that drives it?
			
			- Is it a standard connection?

- Rower
	- How much total energy is being put into the erg from the rower/handle? (this is useful for calculating the efficiency of thewhole system)
		
		- How much is going into the elastic versus the flywheel?
	- What speed is the handle moving at?

- How can we collect this data while the flywheel cover is closed while allowing the side dial for drag to be changed?
	
	- Possibly drill a small hole in the mesh for passing cables?
    	- a single twisted pair of ethernet cable or similar should be able to fit through the holes in the flywheel, if not just one cable. should be enough to get the relevant data out


- How much power/information does the built-in cable/motor thing provide?
	
	- Not much power at all, and it probably cant be used as the existing monitor needs it
	- informatin wise it may be better to use the [Concept2 SDK](https://www.concept2.com/service/software/software-development-kit) as the monitor does a lot of the processing of that signal for us

- come up with a set testing workout (step workout?) to test how it works at various rates and powers
- may also be nice to have a way to consistently pull the handle at certain speeds/powers to test the resistance consistently
  - this might be able to be accomplished by droping a wight that's tied around a pulley and using gravity to pull the handle sideways in a repeatable manner

- is there an effective way to crowdsource data from people who are
	interested in this and have the tools to do so (so I dont have to
	spend tons of money on all the tools)

### Phase 1.5 – Research

- What are concept2’s units of Drag Factor? Is it based on the air
	resistance?
	
	- Constant force or no?
- what rpm/torque value is best for power generation?
- How does the concept2 “watts” measurement compare to actual power
	generation? Is it heat watts vs energy watts?

- What type of motor is likely to be best for converting the flywheel
	motion to electricity?
	
	- BLDC

- Do we need a gear system to get more motion, less force, or more
	force, less motion?
	
	- I think this depends on the motor as we’d need to match it’s
		RPM/torque for optimal output

- Is it possible/are there devices that exist to control the power draw on a motor digitally? (i.e. with an arduino?)
  
- Is there a version of Concept2's SDK that suports linux?
  - how about third party implementations
  - can it really be anything platform specific that cant be recompiled or something? like as far as i can tell it should just be interfacing with the monitors via bluetooth/serial

- What has Concept2 changed year to year hardware wise on the ergs? (specifically Re: flywheel) anyhing major that affects this project?
  - i suspect that the device that measures the flywheel's speed/sips power for the monitor changed from the PM2 to the PM3 ergs as i believe thats where they introduced the idea of the flywheel powering the erg while its in use.
    - This seems to be supported by higher numbers in/between experiments 1 and 2 but not 100% sure as those experiments were poorly conducted and not super on-topic
  - would be nice to get datasheets for these parts
- What are the units on the force curve?
  - [Nobody](https://www.c2forum.com/viewtopic.php?f=15&t=190496) [seems](https://www.c2forum.com/viewtopic.php?f=15&t=185074) to know

### Phase 2 – Basic Experiments

- How does the data from phase 1 vary when the flywheel cover is on vs off? 

- How does the data from phase 1 vary when the flywheel cover is covered/sealed as best as possible versus sitting there regularly?

- How does the data from phase 1 vary when the drag factor dial is changed?
	- This will help calibrate the system to match Concept2’s drag Factor later

### Phase 3 – Prototyping/more experiments

- How efficient can we expect the conversion from motion to electricity to be?

- Can this generated power be used for simple stuff (powered speakers, charge phone, charge battery, fan???)? (is there a usable amount of power generated?)

- What affect does taking more power from the flywheel have on the drag factor. How about the erg’s ability to power itself?

- Do we need to make the flywheel heavier?
	- How do you make the flywheel heavier (safely/in a balanced way)?
		- Put a chain around the edge?

- How to prevent the existing fins from slowing the flywheel down via air resistance?
	- Create a new flywheel that can be swapped out?
	- Cover the fins?

- How best to connect the motor to the flywheel?
	- put gear-like teeth or some other grippy surface (like a rubber-wheeled LEGO wheel for testing purposes) around the circumference of the flywheel (either facing outwards like a regular/bike gear, or to with the teeth facing the face of the flywheel) so that there is a gear-like relationship between the flywheel and the motor shaft
	- put a belt around the edge of the flywheel and use that to drive a motor located elsewhere
- Can we use the concept2 SDK for logging data? (watts, s/m, drag factor, flywheel RPM, etc?)

### Phase 4 – Refine

- Can we collect power while keeping the resistance somewhat the same
	(minimal modifications to the flywheel cover?)?
- How much energy can be taken out from the flywheel and used while
	still having the erg be not significantly harder to use?
- How to calibrate the resistance provided by the new system so that
	it matches the air-based/Drag Factor based system
- Can this generated power be (safely) fed back into the house’s power
	grid?

- Can the resistance be customized either with a dial or through
	software by drawing more current/power from the flywheel?
	- Could we just seal the flywheel cover to remove as much air
		resistance as possible and just control drag factor with power
		draw?

### Phase 5 – (Possibly) Commercial Development
- Can we collect power in a way that can be easily added/removed from
	ergs? (i.e. as a replacement flywleel/replacement flywheel casing
	that the user can swap out)
- How cheaply can this all be done?
- What regulations will we need to comply with in order to sell this?
  - possibly EM Interference, UL Listing, others?

### Phase 5.5 – Operations and Support

- What will be neded to support this product?
  - manual? install guide?
- What would operations look like?

### Phase 6 – Future Complimentary Products

- Can other sources of power (gutter/rainwater generators, etc) be
	used to augment the power from the erg to add more ways to power a
	house? (this is kinda the ultimate vision)
	- Convert a real bike? (greenmicrogym already did this)


# Materials
## Tools

- optical tachometer
	- Homemadeparts
	- IR emitter and receiver LED
	- 10k pot
	- black athletic tape
	- Probably easier to just buy one and/or get someone who has one to collect the data


## Parts
- Stuff I already have lying around
	- Arduino UNO
	- 2.5mm audio jack to capture info from C2 provided cable/power generator
	- some salvaged and unused 18650's from old laptop batteries


# Research, Ideas and Brainstorming

## Parts and Sourcing
### Monitoring Devices

- https://www.thegreenmicrogym.com/2013/09/05/ensupra/
- Kill-A-Watt or similar watt meter for the wall once we get to the stace of putting power into a house

### Energy storage

- ultracapacitors?
- https://www.thegreenmicrogym.com/2013/07/08/diy-off-the-grid-with-the-upcycle-eco-charger/
- https://www.thegreenmicrogym.com/2015/07/13/the-history-of-the-upcycle-ecocharger-how-it-came-to-be/
- Batteries
- 18650's?
- battery charge controller/s
- safety shutoffs/containment for anything that can explode


### Energy Conversion
#### Inverter
- Power conditioning system (probably built into the inverter???)

#### Rectifiers
- ssdlkjele SQL 40V 1000A [seems to be the one from the kit](https://youtu.be/rM7MSq_2Bp4?t=24)
- Some ebay listings at the time of research: [cheap from china](https://www.ebay.com/itm/331245533043), [ships from US](https://www.ebay.com/itm/272885248944).
- need a better source for these (digikey or similar, although I havent checked)

### Motors: 
- [the motor in the kit](https://www.ebikekit.com/blogs/news/upcycle-eco-charger-a-powerful-bicycle-generator) is an ebike motor
- [Guide to ebikeKit Motors](https://www.ebikekit.com/blogs/news/the-ultimate-guide-to-e-bikekit-hub-motors)

- [What types of motors work best as generators](https://www.youtube.com/watch?v=cJ_vDA7xsGs)
- Despite the poor results of the BLDC motor in the video, it seems to me like this was due to the fact that it had a gearbox and wasnt spinning optimally
- [information about 3 phase AC using BLDC motors](https://www.youtube.com/watch?v=quABfe4Ev3s)

#### Option 1: homemade (WPI did this)
- magnets x lots
- copper wire x lots
- some disks to mount to the flywheel axle
- oh dear oh god how to keep it balanced
	- measuring. lots of measuring
- nope
#### Option 2: Purchace new/used
- BLDC
- treadmill motors (would 90v work? seen that number somewhere)
- ebike motors

### Option 2.5: use something that exists
- Tacx bikes
	(https://www.ebay.com/itm/Tacx-Cycleforce-T1670-Bike-Trainer/324395584540?hash=item4b877bcc1c:g:vv8AAOSwPktfws-D)



## Physics 
- [efficiency + flywheels](https://www.resilience.org/stories/2011-06-01/bike-powered-electricity-generators-are-not-sustainable/)



## Planning
### Ideas for Ways to connect motor and flywheel
- belt
- chain
- gears
- fabricate a new flywheel that mounts the same way as the stock one?



## Misc

- [old C2 forum posts of people taling about similar ideas](https://www.c2forum.com/viewtopic.php?t=5334)

- [Green Microgym UpCycle EcoCharger Kit](https://www.thegreenmicrogym.com/product/upcycle-ecocharger-diy-kit-250-grid-tied/)
- “Provides resistance as RPM’s go up” – probably not what I want.
- [how the kit works video](https://youtu.be/rM7MSq_2Bp4?t=24)
- based on the 3 wires from the motor, its almost certainly a BLDC


### World records for erg power generaton

- https://phys.org/news/2012-07-world-rowers-electricity-power-house.html