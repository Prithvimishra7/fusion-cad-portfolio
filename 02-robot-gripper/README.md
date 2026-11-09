# Parallel-Jaw Robot Gripper (Rack & Pinion)

A servo-driven parallel-jaw gripper designed in **Autodesk Fusion**, built for a small robot arm and a Webots sorting cell. One SG90 servo turns a pinion that drives two opposing racks, so both fingers open and close in parallel.

![Final render](Gripper_render.png)

## Features

- **Drive:** SG90 micro servo with a 16-tooth pinion (module 1, 16 mm pitch diameter)
- **Mechanism:** two opposing racks sliding in guide rails on a 70 × 44 mm base plate
- **One jaw part used twice:** the second jaw is the same part rotated 180°, keeping the design simple and printable
- **Travel:** 15 mm per jaw, 0–30 mm total opening
- **Mounting:** servo hangs under the base on two standoffs, shaft through the base into the pinion

## How it moves

| Joint | Type | Notes |
| --- | --- | --- |
| Pinion | Revolute | rotates on the servo shaft |
| Jaw 1 | Slider | travel 0 to −15 mm |
| Jaw 2 | Slider | travel 0 to +15 mm |

The pinion and both jaws are connected with **motion links**: one pinion turn moves each rack 50.27 mm (π × pitch diameter 16 mm). A **motion study** animates the full open/close cycle (about 107° of pinion rotation for full opening).

## Problems solved

| Problem | How it was found | Fix |
| --- | --- | --- |
| Pinion sitting 2 mm inside the base plate | Interference check (overlap volume ÷ pinion area ≈ 2 mm) | Re-jointed the pinion to the base hole with the correct offset |
| Second jaw facing the wrong way | Visual check against the first jaw | Systematically tested joint angle and flip combinations |
| Slight tooth rubbing | Interference check (≈1 mm³) | Expected with straight-sided teeth; next version will use involute teeth |

## Deliverables

| File | Description |
| --- | --- |
| [`Gripper_render.png`](Gripper_render.png) | Photorealistic render |
| [`Gripper_motion.mp4`](Gripper_motion.mp4) | Motion study: open/close cycle |
| [`Gripper_drawing.pdf`](Gripper_drawing.pdf) | ISO A3 assembly drawing with parts list (PM-GRP-001, Rev A) |
| [`Gripper_Assembly.f3z`](Gripper_Assembly.f3z) | Fusion archive (opens in Autodesk Fusion) |
| [`Gripper_Assembly.step`](Gripper_Assembly.step) | STEP file (opens in any CAD software) |

## Skills used

Autodesk Fusion · mechanism design · revolute and slider joints · motion links · joint limits · motion study · interference analysis · rendering · engineering drawings

## Next steps

- Involute gear teeth for a 3D-printable version
- Export meshes for the Webots sorting cell
- Mount on the 3-DOF robot arm (Project 5)

## About

Project 2 of a 5-project CAD + robotics portfolio. Previous: [4S2P Battery Module](../01-battery-module-4s2p/).

**Author:** Prithvi Mishra · November 2026
