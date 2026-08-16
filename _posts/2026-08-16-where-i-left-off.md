---
category: update
author: moralcode
---

Hello to anyone still stumbling upon this site.

This was an ambitious project that, as you can probably tell, never really made it past the concept/validation stage. If you were coming here expecting something working, please know that it will likely take a lot of new R&D effort to turn this vision into something functional.


I think the main reason this project fizzled out due to being a solo project. As a single person, it was difficult to find the motivation to  easily runs out of energy and I only has a limited engineering skillset, which ended up not being enough for me to feel confident addressing the challenges that came up.

These challenges follow roughly this train of thought:
1. The axle of a modern Concept2 rower attaches to the flywheel with a one-way bearing that seems pretty precise, so id probably want to reuse the "hub" of an existing Concept2 flywheel so it can be properly spun by the handle of the machine.
2. Concept2's flywheel uses fins to dissipate energy via air resistance, so those would need to be removed (or covered).
3. Concept2 flywheels that I have seen usually place balancing weights on the fins (as well as drilling holes in the backplate), so fin removal or improper covering can un-balance the flywheel, creating a potentially dangerous spinning object moving at 700-900 RPM.
4. Using just the hub may not be sufficient since you would be removing the majority of the flywheel's mass, so you'd have very little momentum in the new flywheel to "store" energy from the stroke and allow it to be pulled out by the generator in a way that approximates the feel of the original flywheel.
5. You will likely need a very low-friction way to connect the flywheel to the generator. I don't have the Mechanical Engineering skills for most of this, but options ive thought of include:
   - Somehow weld a gear to the outside of the inner flywheel hub and use it to drive a belt or chain connected to the generator (probably easiest mounting, easiest generator sourcing, but this option is quite high-friction as the chain/belt is constantly flexing)
   -  somehow attach the generator directly to the flywheel (see [Figure 1](#figure-1), this is probably the lowest friction option, but the hardest to mount since the generator would be next to the flywheel and occupying the space where the cover would go, necessitating a whole new mounting solution to take the generators weight)
6. Even if you got things mounted, a method of sensing the RPM/rotations of the flywheel in near-real-time would be needed. Keeping the hub portion of the Concept2 flywheel would potentially retain the machine's own ability to sense flywheel RPM, but I have yet to fully confirm whether the "clicks" that the Concept2 hub sensors (located behind the flywheel in the erg body) are a signal that is easy to access (see previous experiment blogs on this site).
7. This hub sensor is how the flywheel can power the Concept2 monitor when actively rowing. That may be worth considering from either a "how do we not break that functionality" or a "how can we use this to extract more usable energy" perspectives
8. You might want a way to store the generated power short-term, such as a capacitor bank, 18650's, etc to help smooth out the spikes in generation that come from each stroke.
9. You would need some kind of controller to take connections from this RPM signal, the generator, and your power storage solution and basically run the logic for how and when to extract energy from the generator to mimic a real flywheel
10. You would need to develop an algorithm to do this, which will likely include developing some mechanism by which to measure/quantify/characterize a normal rowing stroke in terms of the resistance that the stock fins provide to the flywheel (ideally across a range of damper settings).
	- Getting this right in a provable/reproducible/testable way is pretty critical because changing how the flywheel spins will almost certainly change how the Concept2 Performance Monitor shows scores, potentially leading to people thinking they are rowing faster/slower than they actually are (when compared to a stock rowing machine)
	- To do this successfully/reproducibly, you may likely need to develop some kind of testing rig/procedure to ensure you can pull the handle of the rowing machine in a consistent way each time as you change things (damper settings etc) to collect the data needed to characterize the stock Concept2 flywheel vs the custom one. This will also likely rely on having a method of measuring the RPM that can be applied equally to both setups.
11. If you want to use the damper setting in your algorithm for a perfect drop-in user experience, you will very likely need to add some kind of sensor to the damper too (which depending on how you installed the motor, may have been removed or destroyed earlier)
12. After all of this, it is unknown whether a useful enough amount of power will be extractable in the first place (my benchmark is, can it charge my phone, so probably around 5v, and 500-1000 mA of current)
13. If, by some miracle, all of the above are resolved, theres also the additional challenge of: Can this be done in a way that can be packaged to be essentially drop-in replacement for the stock flywheel (i.e. fits within the volume of the stock flywheel cover - other than necessary wires, requires as little destructive mounting/new holes etc as possible, doesn't interfere with any features of the rowing machine that make its built-in display not work, etc) 

While my personal progress on this project has been effectively 0 since early 2021, I would be interested to know if anyone makes progress on this. Information on how to contact me is listed on the homepage of this site.

Best of luck!

### Figure 1 

![A diagram showing how a metal block could be attached to the flywheel hub to support motor attachments](../files/updates/flywheel%20direct%20attach%20cross%20section.png)