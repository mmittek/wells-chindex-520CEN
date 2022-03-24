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

When calling Wells-Index it was determined that the inspection can be done at ~$80/hr shop rate. The spindle can be shipped using UPS in a secured package and must include $2500 insurance.


### Motor
Decided to use the Marathon 80T17FH5212 3-phase 220V AC motor with a VFD. 
<img src="https://github.com/mmittek/wells-chindex-520CEN/blob/main/figures/marathon-80T17FH5212-label.jpg?raw=true" alt="Marathon 80T17FH5212 label" width="500" />

### Breakout board 0-10V output configuration
<img src="https://github.com/mmittek/wells-chindex-520CEN/blob/main/figures/mach3-chinese-bob.jpg?raw=true" alt="Typical MACH-3 breakout board" width="700" />

<cite>
"<i>With that breakout board (below) uses the 12-24v combined with the PWM signal on pin 1 (the computer side) to output the 0-10v signal. Don't connect anything to the pin1 output on the breakout board. He was trying to say that in your hal file the PWM output gets connected to the parallel ports pin 1 there. Then the breakout board uses that signal to generate the 0-10v signal. (The pin 1 output on the breakout board is for situations where you are not using the 0-10v signal and want to bring out the output from parallel port pin 1 for other uses.)</i>"
</cite> 
Source: https://forum.linuxcnc.org/38-general-linuxcnc-questions/40438-making-0-10v-output-work-with-spindle-in-hal?start=10


### VFD-based Spindle Speed control
Decided to use the A2-8007M VFD. Manual available here: https://github.com/mmittek/wells-chindex-520CEN/raw/main/doc/A2%20VFD%20Manual.pdf


| PN    | Description (from the manual) | Value range (from the manual)  | Default | Used    | Comment | 
| ------- | -------                       | -------                        | ------- | ------- | ------- |
| 01| Default display content | 1-30000 | 1 | 1 | Value 1 will display the runtime frequency, 2 will show motor's synchronized speed | 
| 02| Initial start up frequency by panel or other method | 0.01-400.00 | 50Hz | 60Hz | ? | 
| 03| Source of runtime frequency with range | 1-7 | 2 | 2 | 2 - panel button, <br>4 - external 0-10V signal | 
| 04| Source of runtime command  | 1-2 | 1 | 1 | 1- panel button, <br>2-external signal control | 
| 05| Clockwise / Anticlockwise control  | 1-3 | 3 | 3 | 1- clockwise only, <br>2-CCW only, <br>3-CW/CCW enable | 
| 06| Stoppping method  | 1-2 | 2 | 1 | 1)stop by itself, <br> 2) stop by deceleration | 
| 07| Start again by external signal  | 1-2 | 1 | 1 | 1) disabled, <br> 2) enabled | 
| 08| Acceleration time from 0-Max (PN10)  | 000.01s-650.00s | 50s | 3s | Number of seconds to reach the max | 
| 09| Decelarion time from Max(PN10)-0  | 000.01s-650.00s | 50s | 3s | Number of seconds to spin down from the max | 
| 10| Maximum runtime frequency  | 000.01-400.00 | 400.00 | 60.00 |  | 
| 11| Minimum runtime frequency  | 000.01-400.00 | 1.5 | 5.0 |  Looked like it wouldn't spin at all  below ~3 | 
| 12| Motor rating frequency  | 010.00-400.00 | 400 | 60.0 |  From the label | 
| 13| Torque compensation coefficient  | 0.0-4.0 | 0 | 0 |  Looks like it's a proportial term for the PID??? | 
| 14| Torque compensation frequency  | 0.01Hz-600.00Hz | 400 | 80 |  Picked something a bit higher than 60Hz? | 
| 15| Startup DC braking voltage  | 1-100V | 30 | 30 |  Kept the default? | 
| 16| Startup DC braking time  | 000.00-650.00s | 0 | 0 |  Kept the default? | 
| 17| Stop DC braking voltage  | 1-100V | 30 | 30 |  Kept the default? | 
| 18| Startup DC braking time  | 000.00-650.00s | 0 | 0 |  Kept the default? | 
| 19| Source of multi-segment speed  | 1-5 | 1 | 1 |  Kept the default? | 
| 20| Multi-segment speed frequency  1 | 000.10-400.00 | 10 | 10 |   | 
| 21| Multi-segment speed frequency  2 | 000.10-400.00 | 10 | 10 |   | 
| 22| Multi-segment speed frequency  3 | 000.10-400.00 | 10 | 10 |   | 
| 23| Multi-segment speed frequency  4 | 000.10-400.00 | 10 | 10 |   | 
| 24| Multi-segment speed frequency  5 | 000.10-400.00 | 10 | 10 |   | 
| 25| Multi-segment speed frequency  6 | 000.10-400.00 | 10 | 10 |   | 
| 26| Multi-segment speed frequency  7 | 000.10-400.00 | 10 | 10 |   | 
| 27| Point move frequency | 000.10-400.00 | 10 | 10 |   | 
| 28| Choice of relay output | 1-6 | 3 | 3 |  1) Stop inverter <br> 2) Run inverter <br>3) Inverter fault <br> 4) Frequency increasing <br>5) Frequency decreasing <br>6) Frequency reached <br>If output is satisfied ON/OFF State reverses  | 
| 29| 2nd Acceleration time | 000.01-650.00 | 2 | 2 |   | 
| 30| 2nd Deceleration time | 000.01-650.00 | 2 | 2 |   | 
| 31| 2nd Decelation stop frequency | 000.01-650.00 | 1 | 1 |  When runtime frequency is larger than this value, acceleration/decelation time defiend by PN08/PN09. When smaller it's PN29 / PN30  | 
| 32| Parameter management  | 1-6 | 1 | 1 |  1) modification enabled<br>2) modification disabled <br>3) initialize for 400Hz<br>4) read OEM parameters <br>5) write OEM parameters <br>6) initialize for 50Hz <br>NOTE: Password for OEM is 61633 | 
| 33| Software version |  |  |  |   | 
| 34| Auto recovery on power loss | 0-99 | 0 | 0 |  0) disabled,<br>99) "do auto recovery in infinite time, starting from low frequency"<br> other)  | 
| 35| Production date |  |  |  |   | 



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
