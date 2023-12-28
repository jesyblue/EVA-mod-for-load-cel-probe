# EVA-mod-for-load-cel-probe
Mod for EVA 3.0  toolhead from RatRig to use a Load Cel for probing the bed

On my new project of a 3D printer with a 500x500x500 print area , inspired by V-core 3.1 from RatRig i had to implement some changes to meet my needs. 

Of course i end up to change almoust every componenet design from the original project.  

In this repository i want to share my implementation of a normal load cell in the toolhead to alow me a quick and precise bed meash and bed probing. 


![toolhead_1](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/9e7450ed-edba-4923-81b9-e1f34408e90d)

![screen1](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/1eb21f12-e5cd-47b3-97a4-c4f1d3305c2d)


I chose to use two 12mm linear rail monted on a 20x20mm aluminum extrusion with two MGN12HZ0HM linear bearing monted on toolhead. 

![toolhead_2](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/66fae493-ef00-4cc3-9d34-926b695ce393)

the tool head have falowing components >


- LGX Lite Extruder V2 by Bondtech
- Hotend CHC V6 24V
- BIGTREETECH EBB36 V1.2 (on canbus)
- BIGTREETECH KNOMI V1.0

My approach was to use a separat microcontroller to manage the load cell. All what was needed is 

a normal load cel for 5kg with HX711 board.    
 
![load cel](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/e22c20d9-a02f-4fc5-976a-c6e34dcd9f54)

and a Arduino Pro Micro (Mega 32U4)
![Arduino Pro Micro](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/9284fbd1-3b00-48d9-b687-73e08f919ee1)
