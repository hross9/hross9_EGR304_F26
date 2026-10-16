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


### 5V Power Supply

| **Component** | **Image** | **Pros** | **Cons** |
| --- | --- | --- | --- |
| [E36155A](https://www.keysight.com/us/en/product/E36155A/800w-autoranging-power-supply-60v-40a.html) | <img width="202" height="100" alt="image" src="https://github.com/user-attachments/assets/358d89a0-a2e7-4c63-ada9-3a1f08d573ed" /> | * Highest power capabilities (60V) <br> | * Big and clunky <br> * Must be plugged in |
| [U280-C02-63W-1B](https://assets.tripplite.com/product-pdfs/en/u280c0263w1b.pdf) | <img width="202" height="202" alt="image" src="https://github.com/user-attachments/assets/7c32d835-872f-4b74-b5c4-a0900a7f2426" /> | * Uses power from car <br> * Built-in overload protection | * Wires can get in the way <br> * Requires external wires to use |
| [TPS61023](https://www.ti.com/lit/ds/symlink/tps61023.pdf?ts=1792177626548&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS61023%253Futm_source%253Dgoogle%2526utm_medium%253Dcpc%2526utm_campaign%253Dapp-null-null-GPN_EN-cpc-pf-google-ww_en_cons%2526utm_content%253DTPS61023%2526ds_k%253DTPS61023%2526DCM%253Dyes%2526gclsrc%253Daw.ds%2526gad_source%253D1%2526gad_campaignid%253D1767856010%2526gbraid%253D0AAAAAC068F0oyaqHJ2Oh4uIsZP741-gBE%2526gclid%253DCj0KCQjwlsfWBhD4ARIsACL7p1EdeMPRx9YUAtUirNsVwpmqgCDs45rXC0VRQaZiPj_Cubm2MSSXyg8aAh6kEALw_wcB) | <img width="202" height="180" alt="image" src="https://github.com/user-attachments/assets/e180acb4-4f9c-4816-a62e-cac7578fd662" /> | * Most portable option <br> * Attached to subsystem <br> * Smallest option | * Requires small battery <br> * Variable max output |

Decision: [TPS61023](https://www.ti.com/product/TPS61023?utm_source=google&utm_medium=cpc&utm_campaign=app-null-null-GPN_EN-cpc-pf-google-ww_en_cons&utm_content=TPS61023&ds_k=TPS61023&DCM=yes&gclsrc=aw.ds&gad_source=1&gad_campaignid=1767856010&gbraid=0AAAAAC068F0oyaqHJ2Oh4uIsZP741-gBE&gclid=Cj0KCQjwlsfWBhD4ARIsACL7p1EdeMPRx9YUAtUirNsVwpmqgCDs45rXC0VRQaZiPj_Cubm2MSSXyg8aAh6kEALw_wcB)

Rationale: This is the smallest and lightest option that doesn't require the user to need wires. It can be used with a removeable battery for easy switching for the driver. It's also the most portable option, allowing the user to use the device outside of their car, if necessary.
