---
title: Component Selection
---
### Photoresistor

| **Component** | **Image** | **Pros** | **Cons** |
| --- | --- | --- | --- |
| [GL5528](https://cdn.sparkfun.com/datasheets/Sensors/LightImaging/SEN-09088.pdf) | <img width="227" height="202" alt="image" src="https://github.com/user-attachments/assets/57ecbba7-d877-46f4-a6b3-2bb05f8d1de8" /> | * Verified to work <br> * Average values for maximum voltage and gamma value <br> | * Least detailed datasheet <br> * Lowest spectral response peak (540nm) |
| [NSL-06-062(S)](https://www.lasercomponents.com/fileadmin/user_upload/home/Datasheets/apx/ldr-cds/nsl-06-062s-photoresistor.pdf) | <img width="202" height="202" alt="image" src="https://github.com/user-attachments/assets/378d53b5-c412-41a3-8449-c78ec5857c7e" /> | * Highest gamma value at 10-100lux (0.8) <br> * Highest spectral response peak (550nm) | * Not epoxy coated <br> * Lowest maximum voltage (100V) |
| [GL205](https://www.futurlec.com/Datasheet/PHOTOCELL20-24.pdf) | <img width="202" height="202" alt="Image_Name_ALT_Text_7mm-ldr-photo-cell-gl20528-front" src="https://github.com/user-attachments/assets/8b935e8f-f82c-49a1-bc6f-38ddd8e6720f" /> | * Highest maximum voltage (500V) <br> * Most extensive datasheet | * Lowest gamma value at 10-100lux (0.6) <br> * Only orderable in bulk |

Decision: [GL5528 Photoresistor](https://www.digikey.com/en/products/detail/adafruit-industries-llc/161/7244927?gclsrc=aw.ds&gad_source=4&gad_campaignid=20232005509&gbraid=0AAAAADrbLlghrPyvXLrPg3m3T1wVtLSSQ&gclid=Cj0KCQjwlsfWBhD4ARIsACL7p1Gs1Re1WjRknGEnYR6AcgBT01ohwsJThIAH7qotEncfS8NFPYIH8XIaAulUEALw_wcB)

Rationale: This photoresistor is the most commonly used model in Arduino kits because its values are average across the board. While it doesn't have the highest maximum voltage, the design of the subsystem won't need it to exceed 100V. The higher gamma value of NSL-06-062 be a benefit, but the higher sensitivity could lead to issues with detecting the street lights at night.


### Op Amp

| **Component** | **Image** | **Pros** | **Cons** |
| --- | --- | --- | --- |
| [LM741](https://www.ti.com/lit/ds/symlink/lm741.pdf?ts=1792133297459&ref_url=https%253A%252F%252Fwww.google.com%252F) | <img width="202" height="203" alt="images" src="https://github.com/user-attachments/assets/f2b68d05-8037-48b6-872b-26caf2586b15" /> | * Highest maximum voltage (22V) <br> * High supply current (1.7mA) | * Least amount of pins <br> * Slow speed (0.3μs) |
| [OPA4131](https://www.mouser.lt/datasheet/2/405/1/opa2131-3378433.pdf?srsltid=AU7gw4VSwDB3jjYmfcTxapQW_-RNcMZ_ASecxWgroQk72N-GseNanAb_) | <img width="202" height="150" alt="images" src="https://github.com/user-attachments/assets/511864fc-f093-40d1-a6e5-966b7064e205" /> | * Most amount of pins (tied) <br> * High bandwidth (4MHz) | * Unknown supply current rating |
| [MCP6004](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6001-1R-1U-2-4-1-MHz-Low-Power-Op-Amp-DS20001733L.pdf) | <img width="202" height="150" alt="images" src="https://github.com/user-attachments/assets/1b9286c2-ef9e-4cf6-b0fb-b4737dfb0bf0" /> | * Most amount of pins (tied) <br> * Rail to rail capability <br> * Very low power drain (100μA) | * Lowest maximum voltage (7V) <br> * Low speed (0.6μs)|

Decision: [MCP6004 Op Amp](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-E-P/683200?gclsrc=aw.ds&gad_source=4&gad_campaignid=20790518593&gbraid=0AAAAADrbLlj9e9v2l5ZoXiQXj-mZfwT04&gclid=Cj0KCQjwlsfWBhD4ARIsACL7p1FRRpYYM2vDoTMOlRBfY9U3C-MRHVG29ICceAqWETGvv6DikcfNfpgaAtHeEALw_wcB)

Rationale: This Op Amp is the most powerful of the three with the rail-to-rail capabilities and low power drain. It has enough pins to work for the subsystem without adding extra pins like the OPA4131. Can operate on voltages as low as 1.8V, which is within the calculated range for this subsystem.


### 5V Regulator

| **Component** | **Image** | **Pros** | **Cons** |
| --- | --- | --- | --- |
| [LM2940T](https://www.ti.com/lit/ds/symlink/lm2940-n.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792167838898&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Flm2940-n) | <img width="202" height="195" alt="22caa1e5-1ccd-44c0-9487-35516a70ef43" src="https://github.com/user-attachments/assets/919051b8-6974-4c1c-9441-89c116ec967c" /> | * Easy to solder <br> * Built in protection <br> * Fixed output (5V) | * Expensive ordering <br> * Low input voltage maximum (26V) <br> * Low current output (1A) |
| [MC7805ACTG](https://www.onsemi.com/pdf/datasheet/mc7800-d.pdf) | <img width="202" height="200" alt="dab5daea-638a-401a-81a3-08128a3198ba" src="https://github.com/user-attachments/assets/9b4153c8-f632-4168-a9a8-904a7453af9b" /> | * Low cost <br> * Easy to solder <br> * High max voltage (40V) | * Requires external components |
| [LM7805](https://www.st.com/content/ccc/resource/technical/document/datasheet/41/4f/b3/b0/12/d4/47/88/CD00000444.pdf/files/CD00000444.pdf/jcr:content/translations/en.CD00000444.pdf) | <img width="202" height="201" alt="e9d4c884-5567-4bfd-830c-23e196691f71" src="https://github.com/user-attachments/assets/f1310144-b770-4f3e-82de-835c689af463" /> | * Inexpensive <br> * High max voltage (35V) <br> * Fixed 5v output | * High input voltage requirement (5V) |

Decision: [LM7805](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ABV-DG/3945936)

Rationale: The LM7805 has a high maximum voltage, which is good for accidental shorting. It's also inexpensive.
