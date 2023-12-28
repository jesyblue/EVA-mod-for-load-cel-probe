In klipper what is important is to define probe section and the activation pin 


[output_pin probe_0]
pin: EBBCan:PB9
#pwm: False
#static_value:
value: 0
#shutdown_value:
#maximum_mcu_duration:
#cycle_time: 0.100
#hardware_pwm: False
#scale:

[probe]
pin: EBBCan:PB8
speed: 2
samples: 1
z_offset: 0.5
sample_retract_dist: 5
lift_speed: 2
samples_result: median
samples_tolerance: 0.1
samples_tolerance_retries: 2
activate_gcode:
  G4 P500 #pause
  SET_PIN PIN=probe_0 VALUE=1
  G4 P500 #pause
  SET_PIN PIN=probe_0 VALUE=0
  G4 P500 #pause
  SET_PIN PIN=probe_0 VALUE=1
  SET_LED LED=hotend_rgb RED=1.0 GREEN=1.0 BLUE=0.0
deactivate_gcode:
  SET_PIN PIN=probe_0 VALUE=0
  SET_LED LED=hotend_rgb RED=1.0 GREEN=1.0 BLUE=1.0
 # G4 P500 #pause


Ad some macro for activate and deactivate the probe.

[gcode_macro Enable_probe]
gcode:
  G4 P500 #pause
  SET_PIN PIN=probe_0 VALUE=1
  G4 P500 #pause
  SET_PIN PIN=probe_0 VALUE=0
  G4 P500 #pause
  SET_PIN PIN=probe_0 VALUE=1
  SET_LED LED=hotend_rgb RED=1.0 GREEN=1.0 BLUE=0.0

[gcode_macro disable_probe]
gcode:
  SET_PIN PIN=probe_0 VALUE=0
  SET_LED LED=hotend_rgb RED=1.0 GREEN=1.0 BLUE=1.0
 # G4 P500 #pause
