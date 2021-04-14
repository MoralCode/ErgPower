---
category: experiment
author: moralcode
---
# Experiment 1
**Hypothesis:** Since the erg is able to power itself while being used, is it possible to just use this as a source of power from the erg?

## Test A:
tried using a multimeter to measure voltage from the small aux cord like connector coming from a model C flywheel ergwires with , nothing really happened

**Conclusion:** the voltage is probably fluctuating too fast and possibly too low to measure with my multimeter.

## Test B:
wired + and gnd leads of 2.5mm audio jack directly to arduino to log the values to serial console (with IRSensorRead.ino) and plot them in python (code version used for the experiment is tagged)

**Observations:**
 - data seems very noisy ([test_jack_data.csv](../files/experiments/1/test_jack_data.csv) and  [test_jack_data2.csv](../files/experiments/1/test_jack_data2.csv))
  - from the online parts store from concept2, it seems like on model C ergs, the flywheel sensor may be just data, and on model D’s and up it also generates power. Need datasheets and stuff for these parts
  - Probably need a more professional oscilloscope to actually measure this cuz the data seemed super noisy/not super consistent