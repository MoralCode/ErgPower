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
                this is absolute max though)
              - Use an Optical tachometer and arduino to datalog it
                (maybe there’s a better way and the data can be
                crowdsourced)
        
          - How heavy is the flywheel?
        
          - How much is air resistance affecting the flywheel
        
          - How much torque?
            
              - From WPI paper torque peaked at about 15 NM
        
          - How does the flywheel connect to the axle that drives it?
            
              - Is it a standard connection?

  - How much total energy is being put into the erg from the
    rower/handle? (this is useful for calculating the efficiency of the
    whole system)
    
      - How much is going into the elastic versus the flywheel?

  - How can we collect this data while the flywheel cover is closed
    while allowing the drag factor to be changed?
    
      - Possibly drill a small hole in the mesh for passing cables?

  - How much power/information does the built-in cable/motor thing
    provide?
    
      - Not much if at all, and it probably cant be used as the existing
        monitor needs it

  - come up with a set testing workout (step workout?) to test how it
    works at various rates and powers

  - is there an effective way to crowdsource data from people who are
    interested in this and have the tools to do so (so I dont have to
    spend tons of money on all the tools)

### Phase 1.5 – Research

  - What are concept2’s units of Drag Factor? Is it based on the air
    resistance?
    
      - Constant force or no?

  - How does the concept2 “watts” measurement compare to actual power
    generation? Is it heat watts vs energy watts?

  - What type of motor is likely to be best for converting the flywheel
    motion to electricity?
    
      - BLDC

  - Do we need a gear system to get more motion, less force, or more
    force, less motion?
    
      - I think this depends on the motor as we’d need to match it’s
        RPM/torque for optimal output

### Phase 2 – Basic Experiments

  - How does the data from phase 1 vary when the flywheel cover is on vs
    off? 

  - How does the data from phase 1 vary when the flywheel cover is
    covered/sealed as best as possible versus sitting there regularly?

  - How does the data from phase 1 vary when the drag factor dial is
    changed?
    
      - This will help calibrate the system to match Concept2’s drag
        Factor later

### Phase 3 – Prototyping/more experiments

  - How efficient can we expect the conversion from motion to
    electricity to be?

  - Can this generated power be used for simple stuff (powered speakers,
    charge phone, charge battery, fan???)? (is there a usable amount of
    power generated?)

  - What affect does taking more power from the flywheel have on the
    drag factor. How about the erg’s ability to power itself?

  - Do we need to make the flywheel heavier?
    
      - How do you make the flywheel heavier (safely/in a balanced way)?
        
          - Put a chain around the edge?

  - How to prevent the existing fins from slowing the flywheel down via
    air resistance?
    
      - Create a new flywheel that can be swapped out?
      - Cover the fins?

  - How best to connect the motor to the flywheel?

  - Can we use the concept2 SDK for logging data? (watts, s/m, drag
    factor, flywheel RPM, etc?)

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

  - 
  - Can we collect power in a way that can be easily added/removed from
    ergs? (i.e. as a replacement flywleel/replacement flywheel casing
    that the user can swap out)
  - How cheaply can this all be done?

### Phase 6 – Future Complimentary Products

  - Can other sources of power (gutter/rainwater generators, etc) be
    used to augment the power from the erg to add more ways to power a
    house? (this is kinda the ultimate vision)
    
      - Convert a real bike? (greenmicrogym already did this)

# Process

The goal is to do this in a free and open way so that anyone who is sufficiently interested can pick this up where I left off.

  - ideally videotape experiments or at least the process for setting one up so others can replicate it
  - public Documentation (this repo) for the gory details
  - 

# Parts Needed

  - Parts for homemade optical tachometer
    
      - IR emitter and receiver LED
      - 10k pot
      - black athletic tape

  - misc
    
      - 2.5mm audio jack to capture info from C2 provided cable/power
        generator

  - if homemade generator (WPI did this)
    
      - magnets x lots
    
      - copper wire x lots
    
      - some disks to mount to the flywheel axle
    
      - oh dear oh god oh fuck how will it be balanced
        
          - measuring
    
      - nope

  - scrap motor
    
      - 90v treadmill motor?
    
      - Tacx bikes
        <https://www.ebay.com/itm/Tacx-Cycleforce-T1670-Bike-Trainer/324395584540?hash=item4b877bcc1c:g:vv8AAOSwPktfws-D>
    
      - ebike motors
    
      - what rpm/torque value is best for power generation?
    
      - What RPM/torque does erg output?
        
          - Form the WPI paper max torque of an erg is prob 15 N-M  
            RPM range results from 395 to 780 and angular velocity
            ranges from 41.36 to 81.68 radians per second

  - belt/chain/gears/some way to connect the motor to the flywheel

  - inverter

  - watt meter for the wall

  - battery charge controller?

  - Power conditioning system?

# Research

<https://www.thegreenmicrogym.com/product/upcycle-ecocharger-diy-kit-250-grid-tied/>

“Provides resistance as RPM’s go up” – probably not what I want.

[](https://youtu.be/rM7MSq_2Bp4?t=24)

random other ideas:

<https://www.c2forum.com/viewtopic.php?t=5334>

Rectifiers: ssdlkjele SQL 40V 1000A

<https://www.ebay.com/itm/331245533043> (cheap from china)

<https://www.ebay.com/itm/272885248944> (ships from US)

for the rectifier in the kit: <https://youtu.be/rM7MSq_2Bp4?t=24>

World records for erg power generaton

<https://phys.org/news/2012-07-world-rowers-electricity-power-house.html>

Monitoring:

<https://www.thegreenmicrogym.com/2013/09/05/ensupra/>

power storage:

ultracapacitor???
<https://www.thegreenmicrogym.com/2013/07/08/diy-off-the-grid-with-the-upcycle-eco-charger/>

<https://www.thegreenmicrogym.com/2015/07/13/the-history-of-the-upcycle-ecocharger-how-it-came-to-be/>

efficiency + flywheels

<https://www.resilience.org/stories/2011-06-01/bike-powered-electricity-generators-are-not-sustainable/>

Motors:  
the motor in the kit is an ebike motor:
<https://www.ebikekit.com/blogs/news/upcycle-eco-charger-a-powerful-bicycle-generator>

<https://www.ebikekit.com/blogs/news/the-ultimate-guide-to-e-bikekit-hub-motors>

best motor type: <https://www.youtube.com/watch?v=cJ_vDA7xsGs>

3 phase AC: <https://www.youtube.com/watch?v=quABfe4Ev3s>

  
based on the 3 wires from the motor, its almost certainly a BLDC

