# Mars Sim Pack · GirlsWhoML × PhysicsX Hack

Participant dataset and simulation starter kit for the **GirlsWhoML × PhysicsX Mars Hackathon** (London · 15 September · supported by Cursor).

> **Mission brief PDF:** [`Mars_Hackathon_Mission_Brief.pdf`](./Mars_Hackathon_Mission_Brief.pdf) · tracks, tools, schedule, rules, and judging.
>
> **License / credits / gotchas:** [`LICENSE`](./LICENSE) · [`CREDITS.txt`](./CREDITS.txt) · [`KNOWN_ISSUES.txt`](./KNOWN_ISSUES.txt)

---

## Start here tonight

1. Read the **TL;DR** and pick **one track**.
2. Choose **Open Sandbox** (PDF tools) or **Guided Trajectory** (download one zip below).
3. Open `DATA_NOTES.txt` in that zip. Skim [`KNOWN_ISSUES.txt`](./KNOWN_ISSUES.txt) so you do not overclaim the data.
4. Load the CSV (or images). Make one ML decision move a CAD model or a simple UI. Push before **20:35** (mission brief §08).

---

## TL;DR · What Mars is actually like

- **Air:** Atmosphere exists, but ~1% of Earth's pressure. Almost all CO2, basically no oxygen. Unbreathable even if it weren't so thin.
- **Temperature:** Averages about -60 C. Can hit +20 C at noon near the equator; drops below -100 C at night. Huge swings because thin air can't hold heat.
- **Radiation:** No global magnetic field and barely any atmosphere, so little shielding from cosmic and solar radiation. Habitats need thick walls or underground shelter.
- **Gravity:** ~38% of Earth's.
- **Terrain:** Rocky, dusty, craters, cliffs, canyons. No roads; rovers navigate real hazards.
- **Dust storms:** Can wrap the planet for weeks and block sunlight, which is critical for anything solar-powered.
- **Day length:** A "sol" is ~24 h 40 m, close to Earth, but the night temperature crash is brutal.

**Design preconditions (all tracks):** treat this as a real first city, not a 3-person demo.

1. **100 people** live here. Size habitats, fleets, and life support for a settlement.
2. **~2 Earth years (730 sols)** until the next cheap resupply. Your system has to last that gap.
3. **One dust-storm season** sits inside that window (sols **180-260** in these packs). Sunlight dies. Dust gets bad. Design for it.

---

## Pick your pack

Two ways to work. Same brief, different levels of freedom.

### 1. Open Sandbox Pack

*Freedom to choose your own weights, assumptions, and conditions.*

Use the mission brief PDF as your toolkit map. Pick the libraries and data sources that fit your idea: SpiceyPy, GDAL/rasterio, Gazebo/ROS 2, PyBullet/MuJoCo, OpenFOAM, Blender, scikit-learn, PyTorch, Optuna, and the rest listed under **§03 Tools & Resources** in [`Mars_Hackathon_Mission_Brief.pdf`](./Mars_Hackathon_Mission_Brief.pdf).

Best if you already know what you want to simulate and want full control over model weights, loss terms, and environmental assumptions.

### 2. Guided Trajectory Pack

*Recommended datasets per track · less wrangling, more building.*

Download **one zip** for your track. Each zip is already sized to the 100-person / 730-sol / dust-storm precondition. Open `DATA_NOTES.txt` inside the zip first.

| Track | Download | What it does | Source |
| --- | --- | --- | --- |
| **A · Architecture** | [track-a-architecture-emars.zip](guided-packs/track-a-architecture-emars.zip) | Hourly weather at one settlement site for 730 sols: temp, wind, pressure, dust, plus heating load for 100 people. Use it to design habitats, insulation, or a storm-bunker restaurant. | [EMARS](https://rmets.onlinelibrary.wiley.com/doi/10.1002/gdj3.77) |
| **B · Vehicles & Mobility** | [track-b-vehicles-ai4mars.zip](guided-packs/track-b-vehicles-ai4mars.zip) | Rover photos with terrain labels (soil / bedrock / sand / rock) plus a 2-year logistics timetable (3,130 trips). Use it to score routes or a self-driving Mars train. | [AI4MARS](https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars) |
| **C · Life Support** | [track-c-life-support-hre.zip](guided-packs/track-c-life-support-hre.zip) | Daily O2 / water / food / waste / greenhouse ventilation for 100 people over 730 days, including a solar-killing dust storm. Use it to forecast shortages or run indoor greenhouse air. | [ESA HREDA / Mars500](http://esdcdoi.esac.esa.int/doi/html/data/hre/hreda/8b3a6c3f-e7a0-4fb1-8693-8edd6515d06d.html) |

Browse the unzipped folders on GitHub if you just want to peek: [`guided-packs/`](guided-packs/).

**What is real vs ready-made:** Track B includes 48 real AI4MARS image+label pairs. Tracks A and C (and Track B's trip timetable) are hack-ready tables built from those sources, because the full archives are huge or login-gated. Full citations and license notes: [`CREDITS.txt`](./CREDITS.txt).

---

## Pairing the packs with CAD or a front end

The CSVs and images are inputs. The demo judges remember is usually a **3D model that reacts** or a **small UI that shows the decision**.

| Track | Data signal | CAD / 3D idea | Front-end idea |
| --- | --- | --- | --- |
| **A** | `dust_storm_flag`, `habitat_thermal_load_kw_100p`, hourly temp | Blender / FreeCAD / Onshape: wall thickness, airlock, or restaurant pod that **seals / thickens** when storm=1; animate shutters from the daily summary | Dashboard: sol scrubber, temp curve, "seal now" state driven by the CSV |
| **B** | terrain labels + `terrain_risk_score`, `energy_kwh`, `battery_soh` | CadQuery / Blender: train / rover path extruded over a simple Mars plane; color segments by risk | Map UI: draw route, overlay soil/bedrock/sand/rock, show battery drain over 730 sols |
| **C** | `solar_availability`, `greenhouse_ventilation_m3_per_h`, `cabin_co2_ppm_proxy` | Greenhouse CAD with vents / fans that open wider as ventilation rises; dim grow-lights when solar crashes | Control panel: O2/water gauges for 100 people, red alert on storm days |

Fast path tonight: pandas or a notebook computes one number (seal / risk / vent). Push that number into Blender (`bpy`), Three.js, Streamlit, Gradio, or a static HTML chart. One closed loop beats a perfect model with no UI.

---

## Example ideas · go crazy

Prompts, not ceilings. Remix them.

- **Track A · Architecture:** Mars storm-bunker restaurants that seal and re-route when dust walls hit.
- **Track B · Vehicles & Mobility:** Self-driving train transportation across Mars, scoring every stretch of trackbed for safety and energy.
- **Track C · Life Support:** Indoor air ventilation systems for greenhouses that keep both crew and crops alive through solar blackouts.

---

## Know before you overclaim

Full list: [`KNOWN_ISSUES.txt`](./KNOWN_ISSUES.txt). Short version:

- **A:** simulated weather; storm barely mutes day-night swing; 24 h grid, not a true 24 h 40 m sol.
- **B:** only 48 real images; synthetic masks are identical; trip timetable is invented for the 100-person / 730-sol brief.
- **C:** not raw Mars500 telemetry; CO2 proxy stays mild; cite NASA rate priors + HREDA framing.

Still useful: shared assumptions so every crew designs for **100 people**, **730 sols**, and **one dust season**.

---

## Tracks at a glance

| Track | Build around | Where ML helps |
| --- | --- | --- |
| **Architecture** | Habitats, shielding, regolith structures | Wall thickness vs radiation/pressure, modular layout, thermal stability across day-night |
| **Vehicles & Mobility** | Rovers, cargo, autonomous fleets | Terrain classification, safety/energy route scoring, payload vs range |
| **Life Support** | Energy, water, O2, food closed loops | Ice yield, microgrid demand, greenhouse light/water/CO2 |

Full problem framing, example builds, schedule, and judging rubric: the PDF.

Mentors on the floor cover PhysicsX, 3D modelling, and ML support.

---

*Not affiliated as an official PhysicsX product. Community starter pack for GirlsWhoML × PhysicsX participants. Original pack content: MIT. Upstream datasets: see CREDITS.txt.*
