<div align="center">

<img src="images/headshot.png" width="170">

# Henry Perda

### Mechanical Engineering · Northeastern University

**Mechnical Engineering Major - Minor in Aerospace Engineering**

<a href="mailto:perda.h@northeastern.edu"><img src="https://img.shields.io/badge/Email-333333?style=for-the-badge&logo=gmail&logoColor=white"></a>
<a href="https://www.linkedin.com/in/henry-perda-3b7b4a379"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>
<a href="HENRY_PERDA_SPRING_2027.pdf"><img src="https://img.shields.io/badge/Resume-2E7D32?style=for-the-badge&logo=readthedocs&logoColor=white"></a>

</div>

---

## About

I design hardware that has to survive real loads, from a drone fired out of a mortar tube to machined airbrakes on a high power rocket to fluid hardware for a LOX/kerosene engine. My work spans the full loop: requirements, CAD, analysis, manufacturing, test, and redesign when things break.
<div align="center">

| Project | Role | Focus | Status |
|:---|:---|:---|:---|
| [Mortar-Launched UAV](#mortar-launched-uav) | Founder and Lead Engineer | Composite airframe, deployable wings, flight controller | Active |
| [NUaero Airbrakes](#nuaero-airbrakes) | Engineer | Active drag control, servo housing, electronics bay | Completed |
| [NUaero LRE Quick Disconnect](#nuaero-liquid-rocket-engine-quick-disconnect) | Structures Engineer | Remote N2 fill line disconnect, mechanism design | Detailed design |

</div>

---

## Mortar-Launched UAV

`Founder and Lead Engineer` · `January 2026 to present`

A fixed-wing glider that survives a mortar launch, deploys its wings mid-air, and glides to a precise landing zone. The airframe is packaged inside a 50 mm launch tube, takes roughly 90 m/s of launch velocity in a fraction of a second, and is designed to a $150 per-unit cost.

<div align="center">

| <img src="images/uav-cad-stowed.png" width="400"> | <img src="images/uav-cad-deployed.png" width="400"> |
|:---:|:---:|
| *Stowed configuration for launch* | *Wings deployed for glide* |
| <img src="images/uav-hinge-cad.png" width="400"> | <img src="images/uav-hinge-real.jpg" width="400"> |
| *Rear fuselage hinge mechanism, CAD* | *Rear fuselage hinge mechanism, assembled* |

</div>

### Requirements

| Parameter | Target |
|:---|:---|
| Launch tube diameter | 50 mm |
| Launch velocity | ~90 m/s |
| Launch acceleration | 22 g |
| Range | 1.5 km |
| Landing accuracy | 1 m² landing circle |
| Payload | 0.5 kg |
| Unit cost | $150 |
| All-up mass | 0.65 kg |

### Key Technical Decisions

**Airframe material: PLA to carbon fiber composite.** The first-generation airframe was printed in PLA. Under real launch loads it failed by buckling, which showed that axial stiffness, not strength, was the limiting factor. I redesigned the main structure around a carbon fiber composite boom, roughly 50x stiffer than the PLA design for a small weight penalty. I researched different manufacturing techniques to find carbon shaft desing specfically to ressut euler bucking during compression.**

**Wing deployment.** The wings stow flat along the carbon boom to fit inside the 50 mm tube and swing out on a central pivot after the airframe leaves the barrel. Deployment is electronic so it needs power and onboard software. 50 gram micro servos specced with a stall force of 0.25 kgf*cm were used to actuate hte wings at apogee. enough stall margin was required for the servos to resist the drag on the wings. 

**Rear fuselage hinge mechanism (my design).** The rear fuselage hub packages two control servos around a central socket for the carbon boom. when the hinge rotates the slider/wing assembly rotates outward and translates towar the servo due to the slped geometry of the rear fuselage. precise sla 3d pringing was used to make the surfaces of thehinges mroe accurate. THe man challenge was desinging the system to fit in the compact diameter of 50mm, while holding the wings as close to the center as possible in order to maximize lift surface area. 

**Aerodynamics and control.** Launch power, drag coefficient, lift, and control surfaces were all sized off the range and landing accuracy targets.  The NACA 2412 airfoil was selected for its 12% thickness ratio, which fits a 3 mm spar within the wing at a 2" chord, its moderate camber (2% at 40% chord) for good lift at low angles of attack, and its well-documented performance at low Reynolds numbers

### Analysis and Testing

- we performed CFD via ANSYS Fluent on the entire airframe in launch and glide situations and we also simulated our control surfaces seperatley under a tightermesh to vlaidate their capabilities beofre manufacturing.  
- structural analysis was performed via ANSYS mechanical to validate the main structural assembly ability to withstant 22gs at launch as well as the intricate hinge mechanism ability t deal with bending and vibrations during flight. 

### Results and Next Steps

[Current status, latest test outcome, and what's next.]

---

## NUaero Airbrakes

`Engineer` · `January 2026 to July 2026` · `NUaero, Northeastern`

An active airbrakes module for an L2 high power rocket. Four flaps deploy radially through the airframe to add drag during coast, letting the rocket hit a programmable target apogee instead of overshooting it.

I contributed to the design and manufacturing of the airbrakes module, owned the design and analysis of the servo housing and the electronics bay, and took part in much of the rocket's assembly.

<div align="center">

| <img src="images/airbrakes-machined.jpg" width="400"> | <img src="images/airbrakes-in-rocket.jpg" width="400"> |
|:---:|:---:|
| *Machined airbrakes module* | *Module installed in the airframe* |
| <img src="images/airbrakes-mechanism-cad.png" width="400"> | <img src="images/airbrakes-section-cad.png" width="400"> |
| *Flap mechanism, CAD* | *Airbrakes section overview, CAD* |

</div>

### Requirements

| Parameter | Target |
|:---|:---|
| Rocket class | L2 high power |
| Target apogee | Programmable, 7600ft for this flight |
| Airframe diameter | 6in |
| Max flap deployment | 40mm / 10% drag surface increase|
| Deployment time | 1s |
| Module mass | .5kg |

### Key Technical Decisions

**Rotating plate drives four flaps together.** The flaps sit on pins that ride in curved slots in a central rotating plate. Turning the plate pushes all four flaps outward at the same rate, so a single actuator controls deployment and the flaps stay symmetric. Symmetric deployment matters because uneven drag would pitch the rocket off its flight path. We gaunrateed this by working off a cam based desing where each of the airbrake pedals ar edeployed in unison.

**Machined aluminum construction.** The module housing, plate, and flaps are CNC machined from aluminum alloy. they are subjected to roughly 20 pounds of force so 3d printing was off the table. Aluminum was strong enough in a compact state which was necessary ebcuase there was only 3 inches of space to work with due to the size of the motor case. 
**Integration into the airframe.** The module mounts below the recovery section on a bulkhead tied in with threaded rods, as shown in the section CAD. [How flight loads and ejection loads pass through the module.] [Slot sizing in the airframe tube.]

**Servo housing (my design).** [How it mounts the servo to the module, how it reacts actuation torque, material and manufacturing method.] [Analysis you ran on it.]

**Electronics bay (my design).** The E-Bay contains the pcbs and batterys necessary for flight and operation of the airbrakes. I cross referenced the spec sheetof the components and desinged a 3d printed sled that could attach directly to the structal threaded rods and contain all on board electronic ontrols.


### Analysis and Testing

- [Flap load estimate at max deployment velocity]
- [Bench test of the deployment mechanism]
- [Flight results: predicted vs. actual apogee]

### Results and Next Steps

[Outcome and what you'd change.]

---

## NUaero Liquid Rocket Engine Quick Disconnect

`Structures Engineer` · `September 2026 to present` · `NUaero LRE Team` · `Detailed design`

A remotely actuated quick disconnect for the nitrogen fill line on the team's liquid rocket. During loading, the fill line keeps the propellant tanks pressurized to compensate for cryogenic boiloff. Disconnecting that line by hand would put team members next to a pressurized vehicle, so the QD releases it on remote command seconds before liftoff and lets the whole team stay outside the hazard zone from pressurization through disconnect.

<div align="center">

| <img src="images/lre-qd-cad.png" width="400"> | <img src="images/lre-qd-fea.png" width="400"> |
|:---:|:---:|
| *Quick disconnect assembly, CAD* | *FEA of [component]* |

</div>

### Requirements

The QD is a single point of failure for vehicle fill and disconnect: if the hose doesn't release, the launch doesn't happen. The requirements are built around reliability.

| ID | Requirement | Verification |
|:---|:---|:---|
| REQ-001 | Disconnect the N2 fill line on remote command after pressurization, with no personnel at the vehicle | Test |
| REQ-002 | Complete 100 connect/disconnect cycles with zero failures | Test |
| REQ-003 | Show no visible damage or plastic deformation after 100 cycles | Inspection |

### How It Works

The design is built around off-the-shelf Parker pneumatic couplings (SPHN4 groundside male, SPHC4 airside female). Instead of designing a custom seal, the mechanism only has to do one thing: pull back the connector's release sleeve.

1. The static base is secured to the ground with the linear actuator set to its centered position.
2. The fill hose attaches to the slider, the extension springs are stretched, and the ground and air sides are mated.
3. On remote command, the actuator extends 1/2 in and drives the sleeve pusher, which retracts the connector sleeve and releases the coupling.
4. The springs pull the groundside sled back 1 in, where it stops against polyurethane-padded shaft collars.
5. The actuator retracts 1 in, the airside valve clears, and the QD falls away from the vehicle.

### Hardware

| Component | Function | Manufacturing / Source |
|:---|:---|:---|
| Static base | Grounds the assembly; holds the actuator with a 1/4 in bolt and side moldings | 3D printed |
| Linear actuator | Drives the release (1 in stroke, 17 lbf) | Progressive Automations PA-MC1 |
| Actuator adapter | Ties the actuator to the linear shafts and springs | Waterjet, with predrilled features for easy manufacturing |
| Sleeve pusher | Pushes the connector sleeve to release the coupling | Machined |
| Linear motion shafts | Guide the sled; 3/8 in 1050 carbon steel, 6 in long | McMaster-Carr |
| Sleeve bearings | Oil-embedded 841 bronze, ride on the shafts | McMaster-Carr |
| Extension springs | Music wire; pull the groundside clear after release | McMaster-Carr |
| Shaft collars + pads | Hard stop for the sled, padded with Shore 40A polyurethane | McMaster-Carr |

Purchased hardware comes to roughly $295, with the actuator, shafts, and N2-rated hose making up most of the cost.

### Key Technical Decisions

**Extension springs over compression springs.** Separation can't rely on line pressure, because the QD also has to release when the hose is unpressurized. Springs guarantee the groundside pulls away every time, and extension springs give a more predictable force across the range of positions the sled travels through.

**Linear motion shafts instead of a dual sled.** Moving to guided shafts lets the groundside connector travel with the entire actuated segment before release, then slide back cleanly afterward, using one moving assembly instead of two.

**Spreading the shafts apart (my call).** The first layout didn't leave enough clearance between the flexible hose and the shaft collars. I widened the shaft spacing so the hose can move freely through the full release stroke.

**Polyurethane impact pads.** Analysis showed the sled striking the shaft collars exceeded the allowable axial load. Adding 1/4 in Shore 40A polyurethane pads slows the impact enough to bring it back under that limit.

### Analysis and Testing

- **FEA:** [Component analyzed, load case, peak stress, factor of safety]
- **Impact load:** [Sled impact force with and without the pads, and the allowable axial load]
- **100-cycle unpressurized test (REQ-002, REQ-003):** Planned
- **Pressurized cycle test (REQ-001):** Planned, [X cycles at X psi]

### Status

In detailed design with CAD near complete. Next steps are prototype build, the 100-cycle qualification test, and pressurized release testing.

---

## Outreach

**Roxbury Robotics · Volunteer**

Afterschool program introducing elementary students to robotics, giving kids with fewer resources access to engineering.

---

## Skills

<div align="center">

![SolidWorks](https://img.shields.io/badge/SolidWorks-DA291C?style=flat-square&logo=dassaultsystemes&logoColor=white)
![ANSYS](https://img.shields.io/badge/ANSYS-FFB71B?style=flat-square&logo=ansys&logoColor=black)
![CFD](https://img.shields.io/badge/CFD-1565C0?style=flat-square)
![FEA](https://img.shields.io/badge/FEA-1565C0?style=flat-square)
![Composites](https://img.shields.io/badge/Composite_Layup-424242?style=flat-square)
![Machining](https://img.shields.io/badge/Machining-424242?style=flat-square)
![3D Printing](https://img.shields.io/badge/3D_Printing-424242?style=flat-square)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Embedded](https://img.shields.io/badge/Flight_Controllers-424242?style=flat-square)

</div>
