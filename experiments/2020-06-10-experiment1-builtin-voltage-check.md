---
type: experiment
---
- tried measuring voltage from model C wires with multimeter, nothing really happened
- wired + and gnd leads of 2.5mm audio jack directly to arduino to log the values to serial console (with IRSensorRead.ino) and plot them in python
	- data seems very noisy (test_jack_data.csv and  test_jack_data2.csv)
    - 9600 baud used
    - from the online parts store from concept2, it seems like on model C ergs, the flywheel sensor may be just data, and on model D’s and up it also generates power. Need datasheets and stuff for these parts
    - Probably need a more professional oscilloscope to actually measure this cuz the data seemed super noisy/not super consistent