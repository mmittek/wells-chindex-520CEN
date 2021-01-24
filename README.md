# wells-chindex-520CEN
My journey through the revitalization of the Wells-Index 520CEN Milling Machine with Chinese parts.

![Wells-Chindex 520CEN ](https://github.com/mmittek/wells-chindex-520CEN/blob/main/figures/wells-chindex-520cen-front.jpg?raw=true)


## Videos of operation:
- Control using Xbox 360 (knock-off) Controller https://www.youtube.com/watch?v=8YnuL3tIR1U
- Cutting wood for the first time! https://www.youtube.com/watch?v=NYqySIxauQM

A playlist of raw videos is available here: https://www.youtube.com/playlist?list=PLCtCQeHkrL9PzS3xl5yHUxXoV2bxP6WXG


## Condition I got it in
- Missing controller,
- Chipped-off piece of 3-bolt X-axis ball screw mounting section under the table,
- Spindle motor taken off,
- Z-axis ballnut very loosely attached to the quill,
- All motor wires were cut-off (presumably when the controller was removed),
- Bent shaft on the X-axis motor,
- Missing timing belt on the X-axis motor,
- Misaligned (knocked off) case of the Z-axis motor,
- Very loud spindle bearings.

## Shopping List
https://docs.google.com/spreadsheets/d/1s_YOLKgJNMMGrWSA0En5nyfXTiyMLpXokWZuaWBQwuc

## Wells-Index Model 520CEN Machine Specification
see https://static1.squarespace.com/static/5a4bd3d61f318d36bb3b5067/t/5a5d93edec212dbcc76b6927/1516082158247/520CEN+specs.pdf

|                   | Imperial      | Metric            |
| ----------        | ----          | ------            |
| Table Size        | 10" x 48"     | 254mm x 1219mm    |
| T-Slot Size       | 0.625" W on 2.25" centers     | 15.88mm W on 57.25mm centers    |
| Table Travel - X  | 30"           |   762mm           |
| Table Travel - Y  | 13.75"        | 350mm             |
| Table Travel - Z  | 5.1"          | 129mm             |
| Knee Travel - Z   | 16.5"         | 419mm             |
| Overarm Travel    | 24"           | 609mm             | 
| Spindle Motor     | 5 HP AC (Continuous)              |
| Spindle Speeds    | 28-4400 rpm                       |
| Quill Diameter    | 3.375"        | 85.73mm           |
| Spindle Taper     | 30MMT (NMTB30) or 200KS                    |
| Spindle Breaks    | Automatic                         |
| Ways              | Hand Scraped & hard chrome plated |
| Gibs              | Adjustable X,Y and Knee           |
| Ball Screws       |   1 1/4" Dia.                     |
| Coolant           | Spray mist - automatic and manual |
| Shipping Weight   | 3800lbs       | 1905kg            |
| Machine Height    | 100"          | 2540mm            |
| Floor Dimensions  | 8'W x 7 1/2'D | 2438mm x 2286mm   |
| Electrical        | 3/320-60 (Std.)   | 3/460-60 (OPT)|
| Positioning Accuracy | +-0.0005" | +-0.013mm          |
| Repeatability     | +-0.0002"    | +-0.005mm          |
| Control Resolution | 0.0001"      | 0.001mm           |
| Max Distance Spindle to Table | 15.5" | 393.7mm       |
| Axes Servo Drive | Closed-loop DC motors with encoders |
| Rapid Traverse (X, Y, Z) | 200IPM | 5080mm pm         |
| Programmable Feed Rate (X,Y,Z) | 0.1 to 200 IPM | 0.1 to 5080mm pm |
| Air Requirements  | 60-80 PSI     | 4.2-5.6 kg/cm^3   | 

## Belts and pulleys
| Axis | Belt                   | Motor Pulley  | Ballscrew Pulley  |
| --- | ----                    | ----          |   -----           |
| X   | 240L100, 64T, 1" wide   |  16LF100x5/8* |   32T?            |
| Y   | 300L100, 80T, 1" wide   |  16LF100x5/8**  |   32T?            |
| Z   | 225L100, 60T, 1" wide   |  16LF100x1/2* |  32T?             |
*The pulley has been enlarged to ~14mm to slip onto the shaft of the NEMA34 stepper motor.
**A shim / bushing was made to allow for the pulley to slip onto the shaft of the NEMA34 stepper motor.


## Spindle and motor
Tool found in the spindle: QC30DA30B162 / YY678339, it's NMTB30 / QC30, so fith a fixed dawbar it can be used with a collet set using an adapter.

Great mounting guide from NSK / Feyc: https://feyc.eu/download/aplicaciones/maquinaherramienta/nsk/MachineToolSpindleBearingSelectionMountingGuide.pdf

| Placement         | Top Spindle | Bottom Spindle |
| ------- | ------ | --------- |
| Locking nut | SN07 | ??? |
| Original Bearing | 2x 2MM9107WI DUL C1 | 2x 2MM9108WI CR DUL |
| Dimensions | 35x62x14 | 40x68x15 |
| NSK | 2x 7007CTRDULP4Y  | 2x 7008CTRDULP4Y   |

### Speed control
Decided to use the A2-8007M VFD. Manual available here: https://github.com/mmittek/wells-chindex-520CEN/raw/main/doc/A2%20VFD%20Manual.pdf


| Item    | Description (from the manual) | Value range (from the manual)  | Default | Used    | Comment | 
| ------- | -------                       | -------                        | ------- | ------- | ------- |
| 01| Default display content | 1-30000 | 1 | 1 | Value 1 will display the runtime frequency, 2 will show motor's synchronized speed | 
| 02| Initial start up frequency by panel or other method | 0.01-400.00 | 50Hz | 60Hz | ? | 
| 03| Source of runtime frequency with range | 1-7 | 2 | 2 | 2 - panel button, 4 - external 0-10V signal | 
| 04| Source of runtime command  | 1-2 | 1 | 1 | 1- panel button, 2-external signal control | 
| 05| Clockwise / Anticlockwise control  | 1-3 | 3 | 3 | 1- clockwise only, 2-CCW only, 3-CW/CCW enable | 
| 06| Stoppping method  | 1-2 | 2 | 1 | 1)stop by itself, <br> 2) stop by deceleration | 




## SEM MTS30M4-59 DC Servo Encoder Output
This table breaks down the pinout of the header and wire color scheme of the encoder output.

| Position | Color | Purpose    | 
| -------- | ----- | -------    |
| 1        | -     | Key        |
| 2        | RD    | +5V        |
| 3        | BK    | GND        |
| 4        | -     |   -        |
| 5        | RD/BK | B+ ??       |
| 6        | GR    | B-   ??     | 
| 7        | WH/BK | A-         |
| 8        | OR    | A+         |
| 9        | BL    | Z- (Index) (pulls down on the mark) |
| 10       | WH    | Z+ (Index) (pulls up on the mark) |
