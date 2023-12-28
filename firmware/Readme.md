The code was made in Visuino, i have two versions, one with a OLED display for debug purpose , another one just the code to emulate a probe in klipper.   

The load cell don’t need to calibrate or anything…  just activate the HX711 before probe , reset and wait to probe.  When probe touch the bed will hear a sound on the buzzer (use a active buzzer, don’t need to be driven by code) and send positive probe to klipper. “that's it and that's all”
