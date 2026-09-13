# Mars Sim Pack · GirlsWhoML × PhysicsX Hack

Blank planet. One evening. Build something a first settlement would actually fight to keep.

Participant starter kit for the **GirlsWhoML × PhysicsX Mars Hackathon** (London · 15 September · supported by Cursor). Steal the datasets. Twist the brief. Make the judges lean in.

> **Mission brief:** [`Mars_Hackathon_Mission_Brief.pdf`](./Mars_Hackathon_Mission_Brief.pdf) · tracks, tools, schedule, rules, and the full judging rubric.

---

## TL;DR · What Mars is actually like

- **Air:** ~1% of Earth's pressure. Almost all CO2. Basically no oxygen. Unbreathable even if it weren't so thin.
- **Temperature:** Averages about -60 °C. Can hit +20 °C at noon near the equator; drops below -100 °C at night. Thin air can't hold heat, so the swing is savage.
- **Radiation:** No global magnetic field and barely any atmosphere means almost no shielding. Habitats need thick walls or go underground.
- **Gravity:** ~38% of Earth's. Everything moves differently: people, dust, trains, steam from a kettle.
- **Terrain:** Rocky, dusty, craters, cliffs, canyons. No roads. Every route is a negotiation with the ground.
- **Dust storms:** Can wrap the whole planet for weeks and kill the sunlight. If your idea runs on solar, design for the blackout.
- **Day length:** A "sol" is ~24 h 40 m. Close to Earth. The night crash is not.

**Settlement reality check (all tracks):** design for **100 people** across a **minimum 2 Earth-year (~730 sol)** window. That is the brutal resupply gap, and it should include at least one full dust-storm season.

---

## How to win with the datasets

Judges score more than "it runs." Wire your ML into the criteria that matter:

| Criterion | How to use the packs |
| --- | --- |
| **Innovation & Creativity** | Don't stop at a safe demo. Take the dataset somewhere unexpected: a storm-bunker restaurant that opens only when EMARS says the dust wall is coming; a self-driving maglev that reads AI4MARS terrain like a living map; a greenhouse that breathes with the crew. |
| **Technical Execution** | Show an end-to-end loop tonight: load data (or the coming checkpoint) ? model predicts or optimises ? the design actually changes. Crude and complete beats polished and empty. |
| **Feasibility & Real-World Potential** | Keep the wild idea anchored to Mars physics and the 100-person / 2-year preconditions. If judges ask "does this scale past a cute prototype?", your numbers should already answer. |

Impact & Purpose still wins rooms: solve a problem the first city needs before it gets comfort. Team & Collaboration is your crew chemistry on the night.

---

## Pick your pack

Same brief. Two altitudes of freedom. Go loud either way.

### 1. Open Sandbox Pack

*Your weights. Your assumptions. Your chaos.*

Open the PDF and raid **§03 Tools & Resources**. Mix SpiceyPy, GDAL/rasterio, Gazebo/ROS 2, PyBullet/MuJoCo, OpenFOAM, Blender, scikit-learn, PyTorch, Optuna, CAD-in-Python, whatever gets the idea off the ground.

Best when you already have a wild architecture in your head and want full control over model weights, loss terms, and environmental conditions.

### 2. Guided Trajectory Pack

*Curated Mars data so you spend the evening inventing, not wrangling NetCDF ghosts.*

Pick a track. Grab the recommended dataset. Build the thing nobody else in the room will pitch. **Trained checkpoints and cleaned sample slices are landing in a follow-up drop** so you can load and go without downloading whole archives on the night.

| Track | Recommended dataset | What you get | Example idea (go crazy) | Link |
| --- | --- | --- | --- | --- |
| **A · Architecture** | **EMARS** | Hourly temp / wind / pressure / dust (Mars Years 24–33) for weather-aware structure and thermal design | **Storm-bunker restaurants**: dining pods that seal, re-route airflow, and dim the neon when EMARS forecasts a planet-wrapping dust front. Score the night on radiation shelter + thermal comfort for 100 guests. | [EMARS paper & data](https://rmets.onlinelibrary.wiley.com/doi/10.1002/gdj3.77) |
| **B · Vehicles & Mobility** | **AI4MARS** | ~35k rover images, ~326k terrain labels (soil / bedrock / sand / rock / background) for safe-path intelligence | **Self-driving train across Mars**: an autonomous surface train that segments every metre of trackbed from AI4MARS-style imagery, scores derailment risk, and still ships cargo for a 100-person city through a 2-year duty cycle. | [NASA AI4MARS](https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars) |
| **C · Life Support** | **ESA HREDA (Mars500)** | Real ECLSS + physiological telemetry for closed-loop O2 / water / food / waste forecasting | **Indoor air ventilation for greenhouses**: a crew-aware HVAC brain that balances CO2, humidity, and plant O2 return so the greenhouse feeds both lungs and lettuce when a dust storm kills outdoor solar for weeks. | [ESA HREDA archive](http://esdcdoi.esac.esa.int/doi/html/data/hre/hreda/8b3a6c3f-e7a0-4fb1-8693-8edd6515d06d.html) |

Those examples are prompts, not ceilings. Remix them. Combine tracks in spirit. Make something that feels like a city people would brag about surviving in.

---

## Tracks at a glance

| Track | Build around | Where ML punches above |
| --- | --- | --- |
| **Architecture** | Habitats, shielding, regolith structures, places people *want* to be | Wall thickness vs radiation/pressure, modular layout sequencing, thermal stability across the day-night crash |
| **Vehicles & Mobility** | Rovers, cargo fleets, trains, anything that crosses broken ground on limited watts | Terrain classification, safety/energy route scoring, payload vs range under dust and wear |
| **Life Support** | Energy, water, O2, food, air loops that refuse to die | Ice yield maps, demand-aware microgrids, greenhouse light/water/CO2 tuning from real crew telemetry |

Full problem framing, schedule, and rubric: the PDF.

---

## How to use this repo tonight

1. Read the **TL;DR**. Pick **one track**.
2. Choose **Open Sandbox** (PDF toolkit) or **Guided Trajectory** (table above).
3. Lock one ML decision that moves the design, then get a core loop working before you polish the pitch.
4. Push your crew repo before the **20:35** hard cutoff (mission brief §08).

Mentors on the floor cover PhysicsX, 3D modelling, and ML. Use them. Then go slightly too far.

---

*Community starter pack for GirlsWhoML × PhysicsX participants. Not an official PhysicsX product.*
