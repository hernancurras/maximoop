# WRSC reference boat design
This repository contains some sailing robot reference designs that are freely
available to the public. If you have any problem or suggestion on the design please file an issue. 

Please see MIT LICENCE for further information.

The STL file, is part of the design of Ian Roxborough available on Thingiverse https://www.thingiverse.com/thing:4583051

The whole MaxiMOOP hull family is published on Printables, as print-ready STL files and editable STEP files: [MaxiMOOP Autonomous Sailing Open Water Platform](https://www.printables.com/model/1305302-maximoop-autonomous-sailing-open-water-platform) [4].

## Hull

### MaxiMOOP

[MaxiMOOP](https://www.sailbot.org/maximoop/) is a joint design effort between Prof. Paul Miller from U.S Naval Academy and Aberystwyth University specifically for autonomous sailing.
You can find a preview of the model [here](original-designs/maximoopv3.STL) or download the orignal CAD file [here](original-designs/). 

## Repository layout

| Folder | Content |
|---|---|
| [`original-designs/`](original-designs/) | Original CAD files of the MaxiMOOP hull, as received (not modified). |
| [`plans/`](plans/) | Lines plan, table of offsets and 1:1 building templates for MaxiMOOP V3, derived from [`maximoopv3-2.igs`](original-designs/maximoopv3-2.igs). |
| [`papers/`](papers/) | Reference papers. [`irsc2014-maximoop.pdf`](papers/irsc2014-maximoop.pdf) is the MaxiMOOP paper [1]. |
| [`diagrams/`](diagrams/) | Electrical diagrams. [`Dewi_wiring_diagram.pdf`](diagrams/Dewi_wiring_diagram.pdf) is the reference wiring of Dewi (Aberystwyth University). |

## Geometry inventory of `original-designs/`

### Coordinate convention
All dimensions below are in mm and use the same datums as the drawings in [`plans/`](plans/):
- **u** = distance aft of the stem head (u = 76.22 − x, where x is the IGS/3DM longitudinal coordinate converted to mm).
- **z** = height above the design waterline (DWL). The DWL is the lower edge of the transom.
- **y** = half-breadth from the centreline.

The values were measured from the files themselves:
- IGS surfaces were meshed with gmsh and sliced.
- 3DM parts were measured on their trimmed Brep edges with rhino3dm.

Values marked "≈" are measured, not taken from a written specification.

### Files

| File | Origin | Content |
|---|---|---|
| [`maximoopv3-2.igs`](original-designs/maximoopv3-2.igs) | Rhinoceros, 2016, inches | **MaxiMOOP V3**, 15 trimmed surfaces: hull, keel–hull fillet, fin keel, deck and transom. No rudder, no rig. **Source of every drawing in [`plans/`](plans/).** The zip [`maximoopv3-2.igs_.zip`](original-designs/maximoopv3-2.igs_.zip) holds the same file. |
| [`MaxiMOOPv3 for Toby 2019.3dm`](original-designs/MaxiMOOPv3%20for%20Toby%202019.3dm) | Rhinoceros, 2019, inches | **The most complete V3 model.** Same hull, deck and keel as `maximoopv3-2.igs`, in the same coordinate system, plus **rudder, rudder stock, mast and wing sail** (see below). |
| [`MaxiMOOP V3.igs`](original-designs/MaxiMOOP%20V3.igs) | Maxsurf 6.0, 2015, feet | Earlier V3 iteration: 6 surfaces (hull, keel and rudder). The unit scale in the file header looks inconsistent and should be checked before use. |
| [`MaxiMOOP V3. Hull and Keel fillet.igs`](original-designs/MaxiMOOP%20V3.%20Hull%20and%20Keel%20fillet.igs) | Autodesk Inventor 2015, mm | One solid (39 faces) with its origin at the keel bottom. Overall ≈ 1193 × 354 × 683 mm, which is ≈ 27 mm deeper than `maximoopv3-2.igs` (656 mm). The difference has not been resolved yet. |
| [`MaxiMoop_original.igs`](original-designs/MaxiMoop_original.igs) | Maxsurf, 2011, inches | **Original MaxiMOOP** (first generation), with the keel integrated into the hull through slack garboards. ≈ 1194 × 376 mm, draft ≈ 409 mm, consistent with the 0.41 m draft in Table 1 of [1]. |
| [`maximoopv3.STL`](original-designs/maximoopv3.STL) | Ian Roxborough, [Thingiverse 4583051](https://www.thingiverse.com/thing:4583051) | Watertight single-body mesh, 1190 × 356 × 656 mm. Matches `maximoopv3-2.igs`. |

### MaxiMOOP V3 principal dimensions (from `maximoopv3-2.igs`)

| Item | Value |
|---|---|
| Length overall | 1190.3 mm |
| Length waterline | 1088.0 mm |
| Max beam | 355.6 mm (at u ≈ 683) |
| Beam waterline | 304.1 mm |
| Draft (fin tip) | 474.7 mm |
| Deck height on CL | 181.4 mm at the stem, 126.7 mm at the transom (deck is flat athwartships) |
| Transom | raked 7.1° |
| Fin keel | max thickness 37.5 mm; root chord ≈ 537.5 mm (u 358.4 → 896.0); tip chord ≈ 276.5 mm |
| Displacement at DWL | ≈ 19.9 kg in sea water (computed) |

The V3 matches the "improved MaxiMOOP" proposed in Section 6 and Fig. 13 of [1]:
- a separate fin keel and a separate spade rudder
- ≈ 75 mm more draft than the original (0.41 m + 0.075 m ≈ 0.485 m, against 0.475 m measured)
- ≈ 10 mm more freeboard

### Parts present only in `MaxiMOOPv3 for Toby 2019.3dm`

| Part | Measured geometry | Notes |
|---|---|---|
| **Rudder** | Spade, semi-balanced. Spans from the hull down to z ≈ −289. Trailing edge vertical at u ≈ 1175, which is the transom line. Swept leading edge: u ≈ 1019 at z −100 (chord ≈ 156) and u ≈ 1094 at z −280 (chord ≈ 81). Max thickness ≈ 12.6. | [1] lists three rudder options for MaxiMOOP: attached to the keel, transom-hung, and under-hung spade. The 3DM models the spade option used on the USNA boats ("Mid Life Crisis", "ABoat Time"). |
| **Rudder stock** | Ø 10 on the centreline at u ≈ 1067. Runs from z −147.5 to +157.3, through the hull and ≈ 29 above the deck. About 27 aft of the leading edge at z −150. | A separate Ø 10 circle at z = 0, u ≈ 1045, may mark an earlier stock position. |
| **Mast** | Ø 16 tube on the centreline at u ≈ 404. Heel at z −90 (stepped inside the hull, ≈ 29 above the fillet bottom). Top at z +1110. | Close to the pivot of the free-standing balanced gaff rig in Fig. 5 of [1] (≈ 421 mm aft of the stem). |
| **Wing sail** | Span z 210 → 1110 (900 mm). Planform half-width 210 at the foot tapering to 90 at the head, giving ≈ 0.27 m². Depth ≈ 39 (u 396–435). | Area close to the 0.24 m² voyaging rig of [1]. It is modelled athwartships around the mast, so the chord orientation and pivot point should be confirmed. |
| **Deck** | z 106–181 | Same as `maximoopv3-2.igs`. |

### Open items
- Wall thickness and material of the mast tube and rudder stock, and their bearings.
- Wing sail structure, chord orientation and pivot.
- Origin of the 27 mm depth difference in the Inventor model.
- Unit scale of `MaxiMOOP V3.igs`.

## Plans (MaxiMOOP V3)

All drawings are derived from [`maximoopv3-2.igs`](original-designs/maximoopv3-2.igs) and use the coordinate convention above. Revision: **rev2** (2026-11-21), in which the fin keel is included in every drawing. Rudder R1 (balanced, transom-hung) added on 2026-11-21.

| File | Content |
|---|---|
| [`MaxiMOOP_V3_lines_plan_rev2.pdf`](plans/MaxiMOOP_V3_lines_plan_rev2.pdf) | Sheet 1, A1 at 1:2: profile, plan (half-breadths and waterlines every 25 mm), body plan, buttocks, principal particulars and notes. Sheet 2, A3: table of offsets. |
| [`MaxiMOOP_V3_bulkheads_1to1_A1_rev2.pdf`](plans/MaxiMOOP_V3_bulkheads_1to1_A1_rev2.pdf) | 11 A1 sheets at 1:1: bulkheads B1–B11, transom, fin keel profile, fin keel horizontal sections and rudder R1. |
| [`MaxiMOOP_V3_bulkheads_1to1_A4_tiled_rev2.pdf`](plans/MaxiMOOP_V3_bulkheads_1to1_A4_tiled_rev2.pdf) | The same 1:1 templates tiled on A4 (94 pages, 10 mm overlap), for home printers. |
| [`MaxiMOOP_V3_bulkheads_1to1_rev2.dxf`](plans/MaxiMOOP_V3_bulkheads_1to1_rev2.dxf) | 1:1 templates for laser or CNC cutting. Layers: `HULL_EXTERIOR`, `CUT_PLANKING_3mm`, `CENTERLINE`, `DWL`, `BUILDING_BASE`, `FIN_PROFILE`, `FIN_ROOT`, `FIN_SECTIONS`, `FIN_STATIONS`, `RUDDER_BLADE`, `RUDDER_AXIS`, `RUDDER_STOCK`, `RUDDER_SECTIONS`, `RUDDER_GUDGEONS`, `TEXT`. |
| [`MaxiMOOP_V3_lines_1to1_rev2.dxf`](plans/MaxiMOOP_V3_lines_1to1_rev2.dxf) | Lines plan at 1:1: profile, plan, sections, waterlines and buttocks. |

### Rudder R1: balanced, transom-hung (design proposal)
The project uses a transom-hung rudder, the configuration that "Dewi" used at Aberystwyth University [1]. It replaces the spade rudder in the 2019 3DM model, which has its stock through the hull bottom at u ≈ 1067. The rudder is balanced to reduce steering loads.

| Item | Value |
|---|---|
| Hinge axis | Vertical, u = 1205 (13 mm aft of the transom top edge) |
| Gudgeons | On the transom at z +10 (standoff 28) and z +105 (standoff 16); backing plate inside the transom |
| Blade | Root z −20, tip z −290 (span 270); chord 140 → 100; area 0.0324 m²; AR 2.25; tip corners R12 |
| Section | NACA 0012 (16.8 mm thick at the root, 12.0 mm at the tip) |
| Balance | 28 % of chord forward of the axis |
| Clearance | Root edge at least 14 mm below the hull at every rudder angle up to ±35° (checked against the hull mesh) |
| Stock | Ø 10, z −200 → +160; 60 mm tiller arm at z +150 with a pushrod to the deck servo |

Estimated hinge moment at 1.5 m/s (≈ 2.9 kn). Positive values mean the rudder tends to return to centre:

| Balance | 5° | 15° | 30° |
|---|---|---|---|
| 0 % | +0.36 N·m | +1.31 N·m | +1.98 N·m |
| 28 % (R1) | 0.00 N·m | +0.21 N·m | +0.66 N·m |
| 40 % | −0.16 N·m | −0.25 N·m | +0.09 N·m |

- A balance of 25–30 % cuts the steering load by 75–85 % and keeps the rudder self-centring.
- At 35 % or more the rudder is overbalanced at small angles: the servo must hold it, and it swings hard over if the servo fails.
- The estimate uses a simple model: lift slope 2πAR/(AR+2), CL ≤ 1.05, centre of pressure moving from 25 % to 42 % of chord between 0° and 30°. Verify on the water.

Building conventions used in the templates:
- **Stations:** 0–11, every 100 mm aft of the stem head. Bulkheads B1–B11 sit at u = 100…1100. The transom T is at u = 1176–1190.3.
- **Lines:** black = outside moulded line of the hull. Red = cut line inset 3 mm for strip planking.
- **Building baseline:** z = +220, common to all bulkheads, for building upside down on a strongback.
- **Bulkhead placement:** B1–B6 with the aft face on the station line, B7–B11 with the forward face on the station line, so the bevel always removes material.
- **Fin keel:** B4–B8 include the fin section. The fin root is dashed; cut there to build the fin as a separate piece.
- **Printing:** print the PDFs at 100 % ("actual size") and check the 100 mm scale bar on every template.

## Electrical reference: Dewi (Aberystwyth University)

[`diagrams/Dewi_wiring_diagram.pdf`](diagrams/Dewi_wiring_diagram.pdf) redraws the first-draft wiring diagram of **Dewi** [6]. Dewi is the MaxiMOOP built by Aberystwyth University students for SailBot 2013, where it came third and completed all events, including the 6-hour long-distance race [1]. It is the reference implementation for the MaxiMOOP V3 electrical design. The diagram dates from 01-Oct-2015 and is by C. Sauzé.

### Battery and power distribution
| Rail | Source | Feeds | Wiring |
|---|---|---|---|
| ~7 V (unregulated) | Battery box: **NiMH, 6 cells, 7.2 V** | Rudder servo and sail winch, **directly** | Red/black |
| 5 V | **DC-DC converter 5 V** from the battery | Raspberry Pi and WiFi router | Red/black |
| 5 V | Raspberry Pi USB port | Arduino Nano (control pod) | USB cable |
| 3.3 V | Raspberry Pi / Nano | GPS (serial), compass (I²C) | Red/black |

- The servos run from the battery voltage (about 7 V), not from a regulated rail. Their current peaks therefore never load the 5 V logic supply.
- Notes on the original diagram:
  - (*) USNA's *ABoat Time* used a **12 V 20 Ah LiFePO4** battery with a **20 W solar panel** instead.
  - (**) The WiFi router was later replaced by the Raspberry Pi's own WiFi.
- The connector to the WiFi antenna is a waterproof **Bulgin 400** series connector.

### Computing (MCU / CPU)
| Unit | Role | Links |
|---|---|---|
| **Raspberry Pi** (drawn as Raspberry Pi 3B+, ARM 32-bit Linux) | High-level control, logging, telemetry | Ethernet → WiFi router; serial → XBee radio; serial (3.3 V, TX/RX) ← GPS; USB ↔ Arduino Nano |
| **Arduino Nano (ATmega328), "control pod"** | Timing-critical I/O: servo commands, compass, wind vane | USB ↔ Pi; I²C → compass; wind vane input; 2 servo signals → multiplexer |
| **Pololu 4-channel RC servo multiplexer (#2806)** | Hardware switch between manual and autonomous control | RC receiver (rudder/sail) and Nano (rudder/sail/GND) in; yellow servo signals out to the rudder and the sail winch |

- The paper describes the same split [1]. The Pi runs Raspbian, takes the high-level decisions, logs, and sends telemetry over WiFi or an XBee Pro. The Arduino reads the PWM wind sensor and the compass and drives the servos.
- The paper names an Arduino Uno. The diagram and the firmware [7] use an Arduino Nano (ATmega328).
- The firmware [7] is a serial command server at 115200 baud: single-letter commands with one-line JSON replies (compass, pitch, roll, wind, rudder µs, sail µs).
- The Pi runs `boatd`, a daemon that exposes the boat through an HTTP/JSON API. The navigation behaviours run as separate processes.
- **Pi–Nano link over USB.** It also powers the Nano. It avoids connecting 5 V Arduino logic to the Pi's 3.3 V GPIO, so no level shifter is needed.
- **The RC multiplexer is the safety net.** Manual RC control does not depend on the Pi or the Nano firmware. If software hangs, the operator can still take over the rudder and the sail.

### Sensors and actuators
| Device | Type | Connected to | Interface / wiring |
|---|---|---|---|
| GPS + active antenna **ANT555** | Digital | Raspberry Pi | Serial TX/RX at 3.3 V (green/grey). Antenna on BNC, powered from pin 9 / 3.3 V |
| Compass **HMC6343** (tilt-compensated) | Digital | Arduino Nano | I²C (blue/yellow), 3.3 V |
| Wind vane | Analog / PWM | Arduino Nano | 5 V (to be confirmed); read as a PWM pulse width |
| RC receiver | Digital | Pololu multiplexer | Rudder and sail channels (yellow/yellow) |
| Rudder servo | Actuator | Pololu multiplexer | Signal (yellow); power ~7 V from the battery |
| Sail winch | Actuator | Pololu multiplexer | Signal (yellow); power ~7 V from the battery |
| XBee radio + antenna | RF | Raspberry Pi | Serial |
| WiFi router + antenna | RF | Raspberry Pi | Ethernet; antenna through a Bulgin 400 connector |

### Wire colour convention used on Dewi
| Colour | Use |
|---|---|
| Red / black | Power and ground |
| Yellow | Servo signal (rudder, sail) |
| Green / grey | Serial TX / RX (GPS) |
| Blue / yellow | I²C (compass) |

### Considerations carried into MaxiMOOP V3
- Keep a **hardware RC override** (multiplexer) between the receiver, the MCU and the servos.
- Use **separate power rails**: servos on their own supply, logic on regulated 5 V and 3.3 V.
- **Link the Pi and the MCUs over USB or through level shifters**, never 5 V into the Pi's GPIO.
- Use **waterproof connectors** (Bulgin 400 or similar) for every cable that leaves the hull.
- For long missions, plan the power budget around **LiFePO4 + solar + MPPT**, as on ABoat Time, rather than NiMH.

## References
1. P. Miller, M. Hamlet, C. Sauzé, M. Neal, D. Capper, D. Clark, A. Iles, L. Taylor, "MaxiMOOP: A Multi-Role, Low Cost and Small Sailing Robot Platform", in *Robotic Sailing 2014: Proceedings of the 7th International Robotic Sailing Conference* (IRSC 2014), Galway, Ireland, 2014. Local copy: [`papers/irsc2014-maximoop.pdf`](papers/irsc2014-maximoop.pdf). Source: https://www.sailbot.org/wp-content/uploads/2017/06/irsc2014-maximoop.pdf
2. MaxiMOOP at SailBot: https://www.sailbot.org/maximoop/
3. I. Roxborough, MaxiMOOP V3 STL, Thingiverse: https://www.thingiverse.com/thing:4583051
4. MaxiMOOP Autonomous Sailing Open Water Platform (MaxiMOOP hull family: print-ready STL files and editable STEP files), Printables: https://www.printables.com/model/1305302-maximoop-autonomous-sailing-open-water-platform
5. Tools used for the measurements and plans: [gmsh](https://gmsh.info), [trimesh](https://trimesh.org), [shapely](https://shapely.readthedocs.io), [rhino3dm](https://github.com/mcneel/rhino3dm), [ezdxf](https://ezdxf.mozman.at).
6. C. Sauzé, Dewi first-draft wiring diagram (01-Oct-2015), abersailbot/dewi-hardware: https://github.com/abersailbot/dewi-hardware/blob/master/firstdraftwiringdiagramdewi.jpg
7. Aberystwyth University Sailbot, Dewi software (dewi-arduino, boatd, dewi-behaviour): https://github.com/abersailbot
