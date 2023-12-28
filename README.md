# EVA-mod-for-load-cell-probe

Mod for EVA 3.0  toolhead from RatRig to use a Load Cell for probing the bed

On my new project of a 3D printer with a 500x500x500 print area , inspired by V-core 3.1 from RatRig i had to implement some changes to meet my needs. 

Of course, I end up to change almost every component design from the original project.  

In this repository I want to share my implementation of a normal load cell in the toolhead to allow me a quick and precise bed mesh and bed probing. 


![toolhead_1](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/9e7450ed-edba-4923-81b9-e1f34408e90d)

![screen1](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/1eb21f12-e5cd-47b3-97a4-c4f1d3305c2d)


I chose to use two 12mm linear rail mounted on a 20x20mm aluminum extrusion with two MGN12HZ0HM linear bearing mounted on toolhead. 

![toolhead_2](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/66fae493-ef00-4cc3-9d34-926b695ce393)

the toolhead have fallowing components >


- LGX Lite Extruder V2 by Bondtech
- Hotend CHC V6 24V
- BIGTREETECH EBB36 V1.2 (on canbus)
- BIGTREETECH KNOMI V1.0

My approach was to use a separate microcontroller to manage the load cell. All what was needed is 

a normal load cell for 5kg with HX711 board.    
 
![load cel](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/e22c20d9-a02f-4fc5-976a-c6e34dcd9f54)

and a Arduino Pro Micro (Mega 32U4)
![Arduino Pro Micro](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/9284fbd1-3b00-48d9-b687-73e08f919ee1)


The firmware which i made in Visuino must manage the HX711 to his maximum sample rate of 80Hz.  I had to change the board which come with load cell with the green version , this allow me to change the sample rate from 10Hz to 80 Hz putting to VCC pin 15. explained very well here instructables.com/How-to-Convert-Your-HX-711-Board-From-10Hz-to-80Hz

![hx711](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/2ce6e43c-9850-4dd6-b566-2bcc29c56904)
![HX711_mod](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/198999bb-2ecf-425c-b58a-e770c524d350)


this is a section view of the toolhead:

![toolhead_3](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/d9fa7ad1-7121-4a14-84ea-e07c951f3945)


this is the force path:

![toolhead_4](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/3ddb1d4e-8092-497f-951b-c366da8d01f5)

i had to cut about 12,5mm from each end of the load cell to fit inside the toolhead.

![cell_cut_2](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/e8f8badb-7d29-4b65-ae83-6a1d5560c50c)

![cell_mount_2](https://github.com/jesyblue/EVA-mod-for-load-cel-probe/assets/40912320/8101e2a1-75ad-48bb-8f2b-eaed6cc61721)

this is a early test when the code was not fast enough

https://photos.app.goo.gl/1WQfbn4UWSj5rhDH8


