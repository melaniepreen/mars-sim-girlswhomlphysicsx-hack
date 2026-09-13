# Mars Sim Pack — GirlsWhoML × PhysicsX Hack

Participant dataset & simulation starter kit for the **GirlsWhoML × PhysicsX Mars Hackathon** (London · 15 September · supported by Cursor).

> **Mission brief PDF:** [`Mars_Hackathon_Mission_Brief.pdf`](./Mars_Hackathon_Mission_Brief.pdf) — tracks, tools, schedule, rules, and judging.

---

## TL;DR — What Mars is actually like

- **Air:** Atmosphere exists, but ~1% of Earth’s pressure. Almost all CO?, basically no oxygen. Unbreathable even if it weren’t so thin.
- **Temperature:** Averages about ?60 °C. Can hit +20 °C at noon near the equator; drops below ?100 °C at night. Huge swings because thin air can’t hold heat.
- **Radiation:** No global magnetic field and barely any atmosphere ? little shielding from cosmic and solar radiation. Habitats need thick walls or underground shelter.
- **Gravity:** ~38% of Earth’s.
- **Terrain:** Rocky, dusty, craters, cliffs, canyons. No roads — rovers navigate real hazards.
- **Dust storms:** Can wrap the planet for weeks and block sunlight — critical for anything solar-powered.
- **Day length:** A “sol” is ~24 h 40 m — close to Earth, but the night temperature crash is brutal.

**Design preconditions (all tracks):** size for a **100-person** settlement and a **minimum 2 Earth-year (~730 sol)** window — the realistic gap between efficient resupply opportunities, including at least one dust-storm season.

---

## Pick your pack

Two ways to work. Same brief, different levels of freedom.

### 1. Open Sandbox Pack

*Freedom to choose your own weights, assumptions, and conditions.*

Use the mission brief PDF as your toolkit map. Pick the libraries and data sources that fit your idea — SpiceyPy, GDAL/rasterio, Gazebo/ROS 2, PyBullet/MuJoCo, OpenFOAM, Blender, scikit-learn, PyTorch, Optuna, and the rest listed under **§03 Tools & Resources** in [`Mars_Hackathon_Mission_Brief.pdf`](./Mars_Hackathon_Mission_Brief.pdf).

Best if you already know what you want to simulate and want full control over model weights, loss terms, and environmental assumptions.

### 2. Guided Trajectory Pack

*Recommended datasets per track — less wrangling, more building.*

Use the curated Mars datasets below so you can spend the evening on the actual habitat / rover / life-support logic. **Trained checkpoints and cleaned sample data will land in a follow-up commit** — this initial release is the dataset map and guidance only.

| Track | Recommended dataset | What you get | Link |
| --- | --- | --- | --- |
| **A — Architecture** | **EMARS** | Hourly temp / wind / pressure / dust (Mars Years 24–33) for thermal & weather-aware habitat design | [EMARS paper & data](https://rmets.onlinelibrary.wiley.com/doi/10.1002/gdj3.77) |
| **B — Vehicles & Mobility** | **AI4MARS** | ~35k rover images, ~326k terrain labels (soil / bedrock / sand / rock / background) for route scoring | [NASA AI4MARS](https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars) |
| **C — Life Support** | **ESA HREDA (Mars500)** | Real ECLSS + physiological telemetry for closed-loop O? / water / food / waste forecasting | [ESA HREDA archive](http://esdcdoi.esac.esa.int/doi/html/data/hre/hreda/8b3a6c3f-e7a0-4fb1-8693-8edd6515d06d.html) |

**Coming next (second commit):** pretrained / trained artefacts you can load immediately — e.g. weather downscaler checkpoint (Track A), terrain segmenter (Track B), life-support forecaster (Track C) — plus small sample slices so you don’t need to download full archives on the night.

---

## Tracks at a glance

| Track | Build around | Where ML helps |
| --- | --- | --- |
| **Architecture** | Habitats, shielding, regolith structures | Wall thickness vs radiation/pressure, modular layout, thermal stability across day–night |
| **Vehicles & Mobility** | Rovers, cargo, autonomous fleets | Terrain classification, safety/energy route scoring, payload vs range |
| **Life Support** | Energy, water, O?, food closed loops | Ice yield, microgrid demand, greenhouse light/water/CO? |

Full problem framing, example builds, schedule, and judging rubric ? the PDF.

---

## How to use this repo tonight

1. Read the **TL;DR** and pick **one track**.
2. Choose **Open Sandbox** (PDF tools) or **Guided Trajectory** (table above).
3. Scope one decision ML will drive — get a core loop working before polish.
4. Push your crew repo before the **20:35** hard cutoff (see mission brief §08).

Questions on the floor: mentors cover PhysicsX, 3D modelling, and ML support.

---

*Not affiliated as an official PhysicsX product — community starter pack for GirlsWhoML × PhysicsX participants.*
