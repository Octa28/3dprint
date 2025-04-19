# 1. Introduction

## 1.1 Purpose of the Project

The increasing global consumption of plastic—particularly Polyethylene Terephthalate
(PET)—poses significant environmental challenges. PET, commonly used in single-use plastic
bottles, is a durable and recyclable material. However, effective and accessible recycling
solutions are still lacking, especially at the community or educational level. At the same time, the
growth of 3D printing technology presents an opportunity to give this waste stream a second life
in the form of functional, creative, and educational outputs.
This project was developed as a low-cost, open-source system to convert used PET bottles into
3D printer filament. It is designed not only as a tool for sustainability but as a **platform for
education and innovation** , particularly within the framework of **Project Apollo**.
**Project Apollo** is an educational initiative that combines **art, technology, and sustainability** ,
with the mission of teaching young students how these domains interact in practice. Through
hands-on learning, it promotes the development of practical skills and environmental awareness
by guiding students in the fundamentals of electronics, digital design, mechanical systems, and
ecological responsibility.

## 1.2 Objectives

The primary objective of this project is to develop and document an open-source, low-cost PET
recycling and filament extrusion system. This solution is part of **Project Apollo** , an educational
initiative that integrates **arts, technology, and sustainability** to empower young learners
through hands-on experience.
Key goals include:
● Designing a functional and replicable system for converting PET waste into usable 3D
printer filament.
● Introducing students to the fundamentals of **Arduino electronics** , **3D design and
modeling** , and **environmental sustainability** through guided workshops.
● Facilitating learning in **thermal control** , **basic materials science** , and **mechatronics**
using a tangible, real-world application.


● Promoting ecological responsibility and technical literacy among youth, hobbyists, and
community makerspaces.
This system has already been used in student workshops to demonstrate the full lifecycle of
plastic—from waste to digital fabrication material—while teaching the fundamentals of 3D
printing and open hardware.

## 1.3 Background and Motivation

Recycling plastic is a well-understood concept in industrial settings, but the accessibility of
plastic recycling at the consumer level is limited. Most domestic waste plastic ends up in landfills
or oceans, contributing to long-term ecological harm. PET bottles are particularly abundant in
household waste streams and are often single-use items.
Simultaneously, 3D printing is increasingly adopted across various disciplines including
prototyping, education, art, and manufacturing. However, the cost and environmental footprint of
filament materials (typically PLA, ABS, PETG) remain a concern, especially in regions where
imports are necessary.
This project was initiated with the vision of merging **environmental stewardship with
technical innovation** —creating a DIY solution to turn one of the most common types of waste
into a usable product with real-world value.

## 1.4 Overview of the System

The system developed in this project is composed of the following main elements:
● A mechanical frame built from a wooden base and steel brackets, providing stable
support for the extruder and electronics
● An electronics and control unit combining an Arduino Mega 2560 with a RAMPS 1.
board for managing heating and temperature control
● A heating system based on an MK8 hotend extruder, modified with a 2 mm nozzle to
allow smooth manual feeding of PET
● A 12V DC power supply that ensures reliable energy delivery for sustained heating
● A manual filament processing workflow that includes preparing PET bottles, feeding
them into the extruder, and air-cooling the extruded filament


## 1.5 Scope and Limitations

This documentation provides detailed instructions and technical insights into the construction
and operation of the PET filament extrusion system. However, there are several limitations to
consider in its current design. The system has been optimized specifically for PET bottles, and
using other types of plastic may lead to inconsistent extrusion results. Many of the workflow
stages, such as shredding and filament handling, are performed manually, which can affect
repeatability and throughput. Although temperature control is managed through firmware, the
setup does not include automated thermal safety mechanisms, requiring constant supervision
during operation. Additionally, achieving consistent filament quality relies heavily on manual
calibration and experimentation with temperature settings, feed rate, and cooling conditions.
Future improvements may include the integration of automated feeding systems, enhanced
mechanical stability, and the implementation of real-time monitoring and safety features to
increase efficiency and usability, particularly in educational environments.

## 1.6 Target Audience

This documentation is intended for:
● Hobbyists and makers interested in sustainable 3D printing and DIY recycling.
● Students and educators participating in initiatives like Project Apollo, who seek to
combine practical knowledge in arts, electronics, and sustainability.
● Community-based learning centers or fab labs looking to run technical workshops.
● Open-source developers and environmental technology enthusiasts.

# 2. System Overview

## 2.1 Conceptual Overview

This system, developed as part of **Project Apollo** , provides a practical method for converting
used PET plastic bottles into filament suitable for FDM 3D printing. It serves both as a recycling
tool and an educational platform to teach students the foundations of electronics, 3D printing,
and sustainability. The system brings together simple hardware components and open-source
software, designed to be constructed and understood by learners in a workshop setting.
The mechanism is structured to follow a direct and observable process: PET bottles are
collected, cleaned, and thermally processed to prepare the material; they are then manually
inserted into a heated extruder, melted, and transformed into a filament strand. The project


emphasizes low-cost implementation, educational visibility of all components, and modularity for
future upgrades.

## 2.2 System Structure and Workflow

The process begins with the collection and preparation of PET bottles. After removing labels
and cleaning the bottles, a **heat gun is used to gently heat the plastic surface** , making it
smooth and easier to cut or process further. This also helps eliminate creases and uneven
surfaces that could otherwise interfere with consistent feeding into the extruder.
Once the PET material is prepared, it is manually fed into an **MK8 hotend extruder** mounted on
a stable wooden base. The extruder is heated using a 12V power supply and controlled by an
**Arduino Mega 2560** paired with a **RAMPS 1.4 board** running Marlin firmware. The nozzle
temperature is typically set between **200°C and 210°C** , which is sufficient to melt PET while
maintaining material stability.
As the plastic melts and extrudes through the nozzle, it forms a continuous filament strand.
Unlike industrial systems, this prototype does not include a guiding system or an automatic
spooling mechanism. The extruded filament is allowed to **cool naturally in open air** , and the
user must **manually manage the strand** to prevent tangling or curling, typically by slowly
pulling it away from the nozzle and laying it down on a flat surface.

## 2.3 Educational Integration

The system design intentionally avoids hidden components or enclosed mechanisms. All
electronics, wiring, and controls are exposed and accessible, encouraging students to interact
with and understand each subsystem. Through operation and troubleshooting, participants gain
practical knowledge in thermal control, microcontroller programming, sensor interfacing, and
basic mechanical assembly.
This educational value is central to the project’s mission. In **Project Apollo workshops** ,
students engage with the full lifecycle of recycled plastic—from waste to usable filament—while
learning principles of digital fabrication, 3D design, and sustainable engineering.

# 3. Materials & Components

## 3.1 Overview

This chapter details all materials, components, and tools used to construct the PET-to-filament
recycling mechanism. Each item has been selected based on its availability, affordability, and
compatibility with educational use. The list includes electronic modules, mechanical fixtures, and


structural elements, as well as any software tools required for firmware configuration. Where
applicable, the rationale behind choosing each component is also provided to support
replication or customization.

## 3.2 Electronic Components

The control and heating system is built around widely-used 3D printer electronics to ensure
ease of integration and availability.

#### Arduino Mega 2560 (ATmega2560 + CH340)

The central microcontroller board used to run Marlin firmware and control the temperature
regulation and heater output. The Mega 2560 is selected for its large number of input/output
pins, memory capacity, and compatibility with the RAMPS 1.4 expansion board. The CH
variant uses a USB-to-serial converter chip that may require specific drivers when used with
some operating systems.

#### RAMPS 1.4 (RepRap Arduino Mega Pololu Shield)

This board plugs directly onto the Arduino Mega and acts as a shield to interface with
high-current components like heaters, stepper motors, and thermistors. It provides organized
terminals for power and sensor connections, simplifying the wiring of the heating system.

### MK8 Hotend Extruder

The MK MK8 hotend serves as the heating and extrusion component of the system. It includes
a heater block, thermistor, and a brass nozzle originally designed with a 0.2 mm diameter
opening. However, to allow manual feeding of PET strips and enable higher flow rates for
filament extrusion, the nozzle has been modified by drilling it to a 2.0 mm diameter using a
precision 2 mm drill bit.
This modification is necessary because standard nozzle diameters are too narrow for effective
extrusion when using hand-fed plastic strips with varying melt characteristics. The enlarged
nozzle facilitates smoother flow and reduces the likelihood of clogging under manual operation.

#### 12V DC Power Supply

The heating element requires a power source capable of delivering stable current. A 12V power
adapter is connected directly to the RAMPS board’s green terminal block, supplying sufficient
energy to maintain high nozzle temperatures. The USB connection alone cannot power the


heating system, and is used solely for programming and serial communication with the Arduino
board.

## 3.3 Mechanical and Structural Components

#### Wooden Mounting Base

The entire setup is mounted on a solid wood plank that provides physical stability and acts as
the main structure. The surface allows easy mounting of the electronics and extruder using
screws or brackets.

#### Galvanized Steel Joining Brackets

Two steel joining elements are attached to the wood base and are used to firmly secure the
MK8 hotend in place. These elements provide mechanical stability to ensure that the extruder
remains aligned during heating and extrusion.

#### Fasteners and Screws

Standard machine screws, washers, and nuts are used to attach the brackets and secure the
electronic modules to the base.

## 3.4 Additional Tools and Materials

#### Heat Gun

Used to gently heat PET bottles after cleaning and label removal. This step smooths the surface
of the bottle, making it easier to cut and feed into the extruder. It also improves uniformity in the
extrusion process by minimizing surface irregularities.

#### Cutting Tools

Scissors or plastic cutters are used to cut PET bottles into strips or flakes. Although manual, this
step is essential to ensure the pieces are of a manageable size for feeding into the hotend.

#### Computer and USB Cable

A computer is required to upload Marlin firmware to the Arduino Mega and for serial
communication during testing. A standard USB-B cable is used for programming.


## 3.5 Software Tools

#### Arduino IDE

Used to configure and upload the Marlin firmware to the Arduino Mega. This tool allows users to
modify parameters such as maximum temperature limits, sensor types, and safety features.

#### Marlin Firmware

Open-source firmware used to control temperature and outputs on RAMPS-based systems. In
this setup, Marlin has been modified to:
● Recognize the thermistor type
● Set a maximum nozzle temperature of 210°C
● Optionally disable thermal protection (used with caution)

#### Pronterface (Printrun)

A graphical host software used to send G-code commands to the Arduino over USB.
Pronterface allows the operator to set target temperatures (e.g., M104 S210), monitor live
temperature readings (M105), and verify heater response. It serves as the main interface for
operating the heating system during filament extrusion.
All software tools used in this project are cross-platform, free to use, and widely supported in the
3D printing and open hardware communities.

# 4. System Setup & Electronics

## 4.1 Overview

This chapter explains the detailed setup of the electronic components and power connections
that control the PET extrusion system. The system is based on a widely-used configuration
combining an Arduino Mega 2560 with a RAMPS 1.4 shield and an MK8 hotend extruder. This
setup manages temperature control, heating activation, and monitoring via a thermistor, using
Marlin firmware for regulation and communication.
The system was constructed to be open and accessible, with all components mounted on a
wooden plank to allow full visibility of wiring and physical relationships—supporting its
educational use in Project Apollo workshops.


## 4.2 Hardware Assembly

#### 4.2.1 Control Stack Assembly

The **Arduino Mega 2560** is the primary controller and serves as the base layer of the control
stack. On top of this, the **RAMPS 1.4 board** is inserted directly onto the Arduino’s headers. This
configuration allows the Arduino to control high-current components through the RAMPS
board’s MOSFETs and connectors.
The boards are mounted on the wooden base using standard screws or adhesive spacers. Care
should be taken to ensure airflow around the components and avoid shorts from metallic
mounting hardware.

#### 4.2.2 Extruder Mounting

The **MK8 hotend** is held in place between two **galvanized steel joining brackets** , which are
themselves securely screwed into the wooden plank. This method of mounting ensures that the
extruder remains rigid during operation and prevents movement that could affect the
consistency of the extruded filament.
The hotend should be oriented so that the **nozzle points downward** , with enough clearance for
extruded filament to emerge and cool without obstruction.

## 4.3 Wiring Configuration

The wiring follows standard RAMPS 1.4 connections for a heated extruder system. All wires
must be securely inserted and tightened in terminal blocks to prevent arcing or failure during
prolonged heating.
● The **heater cartridge wires** from the MK8 hotend are connected to **D10 terminals** on
the RAMPS board. These are designated in Marlin for the primary extruder heater.
● The **thermistor wires** from the MK8 hotend are inserted into the **T0 (Temperature
Sensor 0)** port on the RAMPS board.
● The **12V DC power supply** has two wires: positive (+) and negative (−). These are
inserted into the **green power input connector** on the RAMPS board, matching polarity.
This external power supply is required to provide enough current to heat the nozzle to
operational temperatures (~200°C), as the USB port cannot supply adequate power.


Before powering on the system, it is important to **carefully inspect all wiring and connections
to ensure safe and proper operation**. The polarity of the power input must be correct, with the
positive and negative terminals from the 12V supply properly aligned with the RAMPS board
input. The heater cartridge and thermistor wires should be firmly inserted into their respective
terminals—D10 for the heater and T0 for the thermistor—to prevent loose connections that
could lead to intermittent heating or inaccurate temperature readings. Additionally, all
components, including the Arduino stack and the mounted extruder, should be securely
fastened to the base to avoid movement or disconnection during operation.

## 4.4 Firmware Configuration

#### 4.4.1 Installing Marlin Firmware

The system is programmed using **Marlin firmware** , uploaded to the Arduino Mega via the
**Arduino IDE**. Marlin is a well-documented, open-source firmware designed for 3D printer
control boards.
The following configuration changes were made in Configuration.h and
Configuration_adv.h:
● **Motherboard definition** set to BOARD_RAMPS_14_EFB (or equivalent)
● **Temperature sensor type** defined to match the MK8 thermistor (commonly type 1 for
100k thermistor)
● **MAX_TEMP** set to 210°C to avoid overheating risks
● **Thermal Runaway Protection** was initially enabled, but later **disabled** after
encountering unexpected shutdowns during heating. This step should only be done in
supervised environments due to safety concerns.
The firmware is compiled and uploaded through a USB connection. Once uploaded,
temperature monitoring and control can be managed via G-code commands or a serial monitor.

## 4.5 Visual Reference

Photos provided below show the actual electronics setup, used as reference in educational
workshops:


**Figure 1 – RAMPS Board Close-Up
Figure 2 & 3 – Electronics Overview**

# 5. Mechanical Structure and Mounting

## 5.1 Overview

The mechanical structure of the PET filament extrusion system is designed for simplicity,
visibility, and stability. The goal is to create a durable yet easily replicable frame that allows
users and students to observe every part of the process. This chapter explains how the
structural base was constructed and how the key components—especially the hotend—are
physically secured to maintain alignment and safety during operation.
The structure is primarily assembled on a wooden plank, selected for its ease of handling,
material availability, and insulation properties. Metal brackets are used to mount and secure the
extruder to the base, ensuring a stable thermal and mechanical interface.

## 5.2 Base Platform Construction

The base of the system is a flat wooden plank, approximately 30 to 40 centimeters in length and
15 to 20 centimeters in width. This provides enough surface area to accommodate the Arduino
Mega with RAMPS board, the MK8 hotend extruder, the power supply terminals, and all
associated wiring and connectors.
The wooden base serves multiple purposes. It offers **electrical insulation** , reducing the risk of
short circuits when mounting exposed components. It also provides **thermal separation** ,
helping to prevent heat from the hotend from transferring to nearby hardware or the work
surface. Additionally, the wood allows for easy mechanical assembly, making it simple to drill
holes or insert screws to secure brackets and components.
Before beginning the mounting process, the wooden surface should be sanded to eliminate
splinters. All component positions should be planned and marked in advance to ensure an
organized and functional layout.

## 5.3 Extruder Mounting Assembly

The MK8 hotend extruder serves as the core of the system and must be rigidly mounted in a
vertical position to ensure consistent extrusion. To accomplish this, two galvanized steel joining
brackets are fixed vertically to the wooden base. These brackets are placed in parallel, with a


spacing that allows the hotend to fit snugly between them. Once positioned, the brackets are
securely fastened to the base using screws, and the hotend is clamped between them.
During installation, careful attention is required to ensure that the heater block is not in direct
contact with the metal brackets. This minimizes unwanted heat transfer into the supporting
structure. The nozzle must also be properly aligned—perpendicular to the base surface and
positioned just above it—to allow the extruded filament to exit cleanly without obstruction.
The hotend can be secured either by utilizing its pre-existing mounting features or through
compression fitting between the brackets. The latter approach works well when the brackets are
closely aligned and the hotend body provides sufficient friction. Regardless of the method, it is
critical that the hotend remains immobile during operation to maintain consistent extrusion and
avoid strain on the electrical connections.
In setting up the orientation, it is also important to plan the position of the brackets and hotend
relative to the base. The hotend should be placed centrally in the structure to allow safe and
comfortable manual access for feeding PET and removing filament. The spacing between
brackets should correspond to the hotend’s body dimensions, typically in the range of 20–
mm, depending on the specific model used.

## 5.4 Electronics Mounting

The Arduino Mega and RAMPS board stack is typically mounted beside the extruder on the
wood base. These components can be affixed using:
● Adhesive-backed PCB standoffs
● Screws with plastic spacers
● Zip ties (temporary setups)
Wires from the RAMPS board should be routed cleanly to the hotend and power supply to
prevent tangling or accidental disconnection. Additional cable management, such as adhesive
clips or spiral wraps, may be used if desired.
Power connectors must remain easily accessible to allow safe disconnection in case of
overheating or failure.

## 5.5 Operating Orientation

During operation, the system should be placed on a stable, level surface with clearance beneath
the nozzle for the extruded filament. Since there is no spool or guiding track, **manual handling**


**of the filament** is required. A flat, heat-resistant surface (e.g., glass or metal sheet) can be
placed underneath the nozzle to allow the filament to cool evenly.
Operators should gently pull the filament away from the nozzle as it is extruded to prevent
curling or buildup. This can be done manually or with a simple support rail, depending on the
use case.

# 6. Plastic Shredding and Preparation

## 6.1 Overview

The quality of the input material directly impacts the consistency and usability of the extruded
filament. This chapter covers the full preparation process for PET plastic bottles prior to
extrusion. It includes the steps of collecting, cleaning, processing, and thermally conditioning the
plastic to ensure it can be smoothly melted and extruded through the hotend. These manual
preparation steps are fundamental for educational environments, as they encourage hands-on
interaction with the raw material and a better understanding of the recycling process.

## 6.2 Collection and Cleaning

The process begins with the collection of used PET plastic bottles. These are typically soft drink
or water bottles, clearly marked with the PET or PETE recycling symbol. It is important to select
bottles that are free from contamination, excessive coloring, or non-PET components.
Each bottle should be rinsed thoroughly to remove any residual liquid, adhesive, or debris. This
cleaning step is essential to prevent residue from burning or clogging the hotend during
extrusion. After cleaning, the bottles are allowed to dry completely to eliminate any internal
moisture, which can cause bubbling or poor filament quality when the plastic is heated.

## 6.3 Label and Cap Removal

Most bottles include plastic labels and caps that are not made from PET. Labels are typically
made of polyethylene or polypropylene, which can interfere with the extrusion process if not
removed. Caps are usually made of HDPE and have a different melting point.
Labels should be peeled off entirely, and any residual adhesive can be scraped or washed away
using warm water and mild detergent. Caps and neck rings must also be discarded, as they are
not suitable for this recycling method.

## 6.4 Thermal Smoothing with Heat Gun


Once the bottles are clean and stripped of non-PET components, they are heated using a **heat
gun**. The purpose of this step is to smooth the bottle’s surface by relaxing folds, bends, or
compression wrinkles that may have formed during use. Heating also slightly softens the plastic,
making it easier to cut into uniform strips or flakes.
The heat gun is passed over the surface of the bottle at a moderate distance to avoid
deformation or premature melting. This process takes only a few seconds and results in a
smooth, flat surface that is easier to process further.
This step is particularly valuable in educational contexts, as it visually demonstrates the effect of
heat on thermoplastics and prepares the material for consistent feeding into the hotend.

## 6.5 Cutting into Strips

After heating, the bottle is cut into long, narrow strips using scissors or sturdy plastic cutters.
The goal is to produce pieces small and flexible enough to be fed manually into the hotend,
while maintaining enough length for continuous feeding during extrusion.
The recommended width of each strip is approximately 5 to 10 mm. Strips that are too wide may
not melt evenly, while strips that are too narrow can slip or feed inconsistently. Bottles can be
cut into spirals or lateral rings to maximize usable material from each unit.
The strips should be free of irregularities, contaminants, or sharp corners that could snag during
feeding. If necessary, edges can be trimmed or smoothed manually.

## 6.6 Material Storage

Prepared PET strips should be stored in a clean, dry container before use. As with filament,
moisture absorption by the PET material can result in extrusion problems such as bubbling or
inconsistent flow. If strips have been exposed to humidity, they should be dried in a
low-temperature oven (around 60°C) or under ambient warm air for several hours prior to
extrusion.
Properly stored and dried strips will melt more consistently and produce smoother, more uniform
filament.

# 7. Extrusion Process

## 7.1 Overview


Once the PET strips are prepared, the next phase is extrusion—converting the manually cut
plastic material into a filament strand through controlled heating. This chapter explains the
procedure for manually feeding the PET into the MK8 hotend, managing temperature, observing
flow characteristics, and maintaining control over the filament output. The extrusion is a critical
point in the recycling process, where mechanical input and thermal control must align for
consistent results.

## 7.2 Preheating the Hotend

Before inserting any material, the hotend must be brought to operational temperature. Using
serial commands or a graphical interface (if connected), the heater is activated and set to a
temperature of **200°C to 210°C**. This range is optimal for melting PET while preventing
degradation.
The hotend should be powered using the external 12V power supply, and monitored for
consistent temperature rise. The thermistor reading should stabilize near the target setpoint.
The system does not use active feedback control beyond the firmware, so visual supervision is
essential. Preheating typically takes 2 to 3 minutes depending on ambient conditions.

## 7.3 Preparing the Plastic Strip for Insertion

For the extrusion to initiate properly, the **leading end of the PET strip must be cut to a sharp
point**. This pointed tip allows the strip to enter the **heating zone of the nozzle** with minimal
resistance. A flat or blunt edge may catch at the entrance of the hotend, preventing feeding and
causing heat accumulation at the entrance.
The strip should be guided slowly into the top of the MK8 hotend, manually pushed in until
resistance is felt. As the tip of the plastic enters the heated section, it begins to soften and melt.
Light but continuous pressure should be applied to maintain forward movement.

## 7.4 Active Extrusion

Once the PET begins to melt, it will start to flow through the nozzle and exit as a thin strand.
This stage marks the start of active extrusion. The operator must continue to **manually feed the
strip** into the hotend at a steady rate, compensating for the melting rate of the plastic.
Feeding too quickly may jam the nozzle, while feeding too slowly can allow the plastic inside the
heater block to overheat or burn. A balance must be maintained, typically using visual feedback
from the filament emerging from the nozzle.
The diameter and clarity of the filament strand should be monitored continuously. Well-extruded
PET will form a **translucent, glossy filament** , with consistent diameter and minimal air
bubbles. Variations in temperature, feeding rate, or strip thickness will affect the filament quality.


## 7.5 Managing the Output

As the filament exits the nozzle, it remains soft for a few seconds before cooling and hardening.
The system does not include a dedicated guide path or automatic spooling mechanism.
Therefore, the operator must **manually manage the filament as it emerges** , gently pulling it
away from the nozzle and laying it on a flat, clean surface.
It is helpful to guide the filament in a straight path to avoid kinks, coils, or sticking, which can
affect its later use in a 3D printer. Allowing the filament to cool in a controlled linear fashion
ensures better handling and storage.

## 7.6 Continuous Operation

To continue extrusion, the operator feeds a new PET strip immediately after the previous one
has nearly been consumed. It is important to prepare the next strip in advance and cut the
leading end to a sharp point before inserting it.

# 8. Filament Cooling, Spooling, and

# Storage

## 8.1 Cooling the Extruded Filament

As the PET exits the hotend in molten form, it must cool quickly and evenly to solidify into
usable filament. The current system uses **natural air cooling** , which means the operator is
responsible for manually managing the extrusion path and ensuring the strand does not fold,
bend, or stick to itself while still soft.
Immediately after exiting the nozzle, the filament remains pliable for several seconds. During
this time, the operator should gently pull the strand away from the nozzle at a steady pace and
lay it out straight on a **flat, clean, and heat-resistant surface**. A non-stick surface such as a
smooth metal sheet, glass plate, or ceramic tile is ideal. This helps maintain a uniform
cross-section and prevents defects such as flat spots, curls, or twists.
Maintaining consistent speed and tension during this phase is essential. Variations in pulling
speed can lead to inconsistent filament diameter, which can impact print quality when the
filament is later used in a 3D printer.

## 8.2 Manual Handling and Temporary Storage


Since the current prototype does not feature a spooling mechanism or output guide, the filament
must be manually handled and stored as it is produced. Once a segment of filament has fully
cooled and hardened, it can be lifted from the surface and coiled loosely by hand.
These coils should be laid flat or loosely wrapped into loops, avoiding sharp bends or tight
curves. Any kinks or deformation introduced during storage can affect feeding into the printer
and may require reconditioning before use.
If a longer segment of filament is produced, it is useful to store it in **large loops with a diameter
of at least 30–40 cm** , tied loosely using twist ties or soft string to prevent tangling. Care should
be taken not to compress or stress the filament mechanically after it has hardened.

## 8.3 Moisture Protection and Long-Term Storage

PET is **hygroscopic** , meaning it readily absorbs moisture from the surrounding environment.
Moisture within the filament can cause poor print performance, resulting in bubbling, uneven
extrusion, or weak layer adhesion.
To protect the filament between production and use, it should be stored in a **sealed container**
with a **desiccant** , such as silica gel packets. Ideally, the storage container should be airtight and
kept in a dry, room-temperature environment.
If the filament has been exposed to humidity, it may be dried using a low-temperature oven or
filament dryer. The recommended drying temperature for PET is around **60°C for 4–6 hours**.
Care must be taken not to deform the filament during this process.

# 9. Technical Specifications

## 9.1 Electrical Specifications

The system operates using low-voltage DC power and standard microcontroller logic levels. The
components are selected to ensure safe integration and ease of power management in a
small-scale or educational environment.
● **Power Supply Voltage:** 12V DC
● **Typical Power Supply Current:** 5–10 A (depending on heating duration and load)
● **Heater Cartridge Voltage Rating:** 12V
● **Arduino Logic Voltage:** 5V (standard TTL logic)


● **Connection Interface:** USB-B (for firmware upload and serial control via Pronterface)
Power is supplied via a dedicated 12V power adapter, which connects to the RAMPS 1.4 board
through the green terminal block. The USB connection to the Arduino Mega 2560 is used only
for programming and control commands; it is not capable of delivering sufficient current for the
heating process.

## 9.2 Temperature Parameters

Accurate temperature control is critical for PET extrusion. The system uses the MK8 hotend and
a thermistor sensor configured in firmware to monitor and regulate the heat.
● **Nozzle Operating Temperature:** 200°C – 210°C
● **Maximum Temperature Set in Firmware:** 210°C (for safety)
● **Heating Time (Ambient to 210°C):** Approximately 2–3 minutes
● **Thermistor Input Port:** T0 on RAMPS 1.
● **Firmware Control Interface:** Marlin (via Pronterface)
The heating is initiated through G-code commands issued from Pronterface. The Marlin
firmware monitors the temperature using the thermistor and toggles the heater accordingly. Note
that thermal runaway protection was disabled for operational reasons, so the system must be
monitored during use.

## 9.3 Mechanical Configuration

The system is built on a manually constructed frame using readily available materials. The
following dimensions are approximate and can be adjusted based on user requirements:
● **Base Platform Material:** Wood plank
● **Base Dimensions:** ~30–40 cm length, ~15–20 cm width
● **Hotend Mounting:** Between two galvanized steel joining brackets
● **Bracket Spacing:** Aligned to fit snugly around MK8 hotend (typically ~20–30 mm)
● **Hotend Orientation:** Vertically mounted, nozzle pointing downward


● **Total Assembly Footprint:** Compact, desktop-scale layout
The structure is fully open and visible, designed for demonstration and educational purposes.
No enclosure or thermal insulation is used in the current prototype.

## 9.4 Filament Output Parameters

The system uses a **custom-modified brass nozzle** with a **2.0 mm opening** , enlarged from the
original 0.2 mm diameter. This adjustment enables effective extrusion of manually fed PET
strips without the need for motorized pressure or gearing. It also supports a wider filament
strand output, which is easier to control during manual handling and air cooling.
**Relevant parameter update:**
● **Modified Nozzle Diameter:** 2.0 mm
● **Expected Filament Diameter:** ~1.5 mm – 2.0 mm

# 10. Safety Guidelines

## 10.1 Thermal Safety

The MK8 hotend reaches operational temperatures of **200°C to 210°C** , which can cause **severe
burns on contact**. The heater block, brass nozzle, and adjacent areas should never be
touched during operation or immediately after powering down.
The heating process is managed via commands sent through Pronterface and monitored using
Marlin firmware. However, the **thermal protection feature in Marlin has been disabled** in this
system to avoid unwanted heater shutdowns during extended use. This increases the risk of
uncontrolled heating if a fault occurs. Therefore:
● The system must be **continuously monitored** while powered and heating.
● Heating should only occur in **ventilated, supervised environments**.
● Operators should use **insulated tools** if interaction near the hotend is required.
● **Never leave the system unattended** while the hotend is active.
Allow the hotend to cool fully before disassembling, storing, or performing maintenance.


## 10.3 Electrical Safety

The system operates with a **12V DC power supply** capable of delivering several amps. While
the voltage is low, the current can cause **short circuits or component damage** if connections
are not properly secured. To reduce risk:
● Always verify correct **polarity** when connecting the power supply to the RAMPS board.
● Ensure **firm wire insertion** into the terminal blocks, particularly at the green input and
the D10 heater output.
● Avoid powering the system without a **heat-resistant base** and **non-flammable
surroundings**.
● Keep **liquids and conductive objects** away from the electronics.
Fig. 1
Fig. 2 & 3


