# WRSC reference boat design
This repository contains some sailing robot reference designs that are freely
available to the public. If you have any problem or suggestion on the design please file an issue. 

Please see MIT LICENCE for further information.

The STL file, is part of the design of Ian Roxborough available on Thingiverse https://www.thingiverse.com/thing:4583051

The whole MaxiMOOP hull family, ready to 3D print as STL files, is published on Printables: [MaxiMOOP Autonomous Sailing Open Water Platform](https://www.printables.com/model/1305302-maximoop-autonomous-sailing-open-water-platform) [4].

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

All drawings are derived from [`maximoopv3-2.igs`](original-designs/maximoopv3-2.igs) and use the coordinate convention above. Revision: **rev2** (2026-11-21), in which the fin keel is included in every drawing.

| File | Content |
|---|---|
| [`MaxiMOOP_V3_lines_plan_rev2.pdf`](plans/MaxiMOOP_V3_lines_plan_rev2.pdf) | Sheet 1, A1 at 1:2: profile, plan (half-breadths and waterlines every 25 mm), body plan, buttocks, principal particulars and notes. Sheet 2, A3: table of offsets. |
| [`MaxiMOOP_V3_bulkheads_1to1_A1_rev2.pdf`](plans/MaxiMOOP_V3_bulkheads_1to1_A1_rev2.pdf) | 10 A1 sheets at 1:1: bulkheads B1–B11, transom, fin keel profile and fin keel horizontal sections. |
| [`MaxiMOOP_V3_bulkheads_1to1_A4_tiled_rev2.pdf`](plans/MaxiMOOP_V3_bulkheads_1to1_A4_tiled_rev2.pdf) | The same 1:1 templates tiled on A4 (79 pages, 10 mm overlap), for home printers. |
| [`MaxiMOOP_V3_bulkheads_1to1_rev2.dxf`](plans/MaxiMOOP_V3_bulkheads_1to1_rev2.dxf) | 1:1 templates for laser or CNC cutting. Layers: `HULL_EXTERIOR`, `CUT_PLANKING_3mm`, `CENTERLINE`, `DWL`, `BUILDING_BASE`, `FIN_PROFILE`, `FIN_ROOT`, `FIN_SECTIONS`, `FIN_STATIONS`, `TEXT`. |
| [`MaxiMOOP_V3_lines_1to1_rev2.dxf`](plans/MaxiMOOP_V3_lines_1to1_rev2.dxf) | Lines plan at 1:1: profile, plan, sections, waterlines and buttocks. |

Building conventions used in the templates:
- **Stations:** 0–11, every 100 mm aft of the stem head. Bulkheads B1–B11 sit at u = 100…1100. The transom T is at u = 1176–1190.3.
- **Lines:** black = outside moulded line of the hull. Red = cut line inset 3 mm for strip planking.
- **Building baseline:** z = +220, common to all bulkheads, for building upside down on a strongback.
- **Bulkhead placement:** B1–B6 with the aft face on the station line, B7–B11 with the forward face on the station line, so the bevel always removes material.
- **Fin keel:** B4–B8 include the fin section. The fin root is dashed; cut there to build the fin as a separate piece.
- **Printing:** print the PDFs at 100 % ("actual size") and check the 100 mm scale bar on every template.

## References
1. P. Miller, M. Hamlet, C. Sauzé, M. Neal, D. Capper, D. Clark, A. Iles, L. Taylor, "MaxiMOOP: A Multi-Role, Low Cost and Small Sailing Robot Platform", in *Robotic Sailing 2014: Proceedings of the 7th International Robotic Sailing Conference* (IRSC 2014), Galway, Ireland, 2014. Local copy: [`papers/irsc2014-maximoop.pdf`](papers/irsc2014-maximoop.pdf). Source: https://www.sailbot.org/wp-content/uploads/2017/06/irsc2014-maximoop.pdf
2. MaxiMOOP at SailBot: https://www.sailbot.org/maximoop/
3. I. Roxborough, MaxiMOOP V3 STL, Thingiverse: https://www.thingiverse.com/thing:4583051
4. MaxiMOOP Autonomous Sailing Open Water Platform (MaxiMOOP hull family, print-ready STL files), Printables: https://www.printables.com/model/1305302-maximoop-autonomous-sailing-open-water-platform
5. Tools used for the measurements and plans: [gmsh](https://gmsh.info), [trimesh](https://trimesh.org), [shapely](https://shapely.readthedocs.io), [rhino3dm](https://github.com/mcneel/rhino3dm), [ezdxf](https://ezdxf.mozman.at).
