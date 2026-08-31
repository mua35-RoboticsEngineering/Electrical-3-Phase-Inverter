# Three-Phase Inverter and PMSM Motor Simulation

This project explores the design and simulation of a three-phase inverter for driving a permanent-magnet motor system. The electrical inverter was developed and analysed in LTspice, while ANSYS Maxwell was used to model the electromagnetic behaviour of the motor load. I did this project as part of my academic studies alongside one of my friends.

The project links two important areas of electric drive design:

- Power electronics and inverter switching
- Electromagnetic motor modelling

The aim was to understand how a DC supply can be converted into a controlled three-phase electrical output and how this output influences the electromagnetic behaviour of a permanent-magnet motor.

## Project Overview

The first stage of the project involved designing a three-phase inverter in LTspice.

The inverter converts a DC input into three controlled phase voltages using three switching legs. Each inverter leg contains an upper and lower switching device, creating the conventional six-switch three-phase bridge arrangement.

Sinusoidal reference signals were generated for phases A, B and C, with each signal separated by 120 degrees. These reference signals were compared with a higher-frequency triangular carrier waveform to generate Pulse Width Modulation (PWM) switching signals.

The LTspice model used:

- 314 V DC bus voltage
- 50 Hz fundamental electrical frequency
- 1 kHz switching frequency
- Three sinusoidal reference signals separated by 120 degrees
- Triangular carrier waveform
- Modulation index of 0.95
- Six-switch three-phase inverter topology

The simulation was then used to investigate the resulting phase voltages, line-to-line voltages and PWM switching behaviour.

## LTspice Inverter Simulation

The inverter model consists of four main areas:

1. DC power supply
2. Three-phase reference signals
3. PWM and switching circuitry
4. Three-phase motor/load representation

The three reference waveforms represent the required output phases of the motor drive.

Each sinusoidal reference is compared against the triangular carrier signal. The result of this comparison determines the switching state of the corresponding inverter leg.

This allowed the inverter to generate PWM phase voltages whose average behaviour follows the required three-phase sinusoidal system.

### Phase Voltages

The phase voltage simulations demonstrate the switching voltage generated independently by each inverter leg.

The phase outputs switch rapidly between the available DC voltage levels as a result of PWM operation. Although the instantaneous waveforms consist of switching pulses, their average behaviour represents the required AC waveform.

The three phase voltages also maintain the required phase displacement between phases A, B and C.

### Line Voltages

Line voltages were also analysed by measuring the voltage difference between two inverter phases.

For example:

`VAB = VA - VB`

The resulting line-to-line voltages contain both positive and negative PWM voltage levels and demonstrate how the switching states of two inverter legs combine to generate the voltage applied between motor phases.

Examining both the phase and line voltages helped build a stronger understanding of how three-phase inverter outputs are formed.

## PWM Control

One of the main concepts explored during the project was sinusoidal Pulse Width Modulation.

Three 50 Hz sinusoidal reference signals were created with a 120-degree phase difference. These signals were compared with a 1 kHz triangular carrier waveform.

The comparison determines when each switching device is activated.

This allowed me to develop a practical understanding of:

- PWM generation
- Switching frequency
- Fundamental electrical frequency
- Modulation index
- Carrier and reference waveform comparison
- Three-phase switching sequences
- DC-to-AC power conversion

## Motor Modelling in ANSYS Maxwell

The second part of the project investigated the electromagnetic behaviour of the motor connected to the inverter.

A two-dimensional electromagnetic model of a permanent-magnet motor was developed using ANSYS Maxwell.

The model included:

- Stator geometry
- Copper stator windings
- Permanent-magnet rotor
- Rotor shaft
- Air gap
- Inner and outer simulation regions
- Material assignments
- Three-phase electrical excitation

A quarter-section of the motor geometry was modelled while retaining the components required to represent its electromagnetic operation.

Transient magnetic analysis was selected because the currents, magnetic field and rotor behaviour vary with time.

## ANSYS Simulation Setup

The motor simulation required several stages of electromagnetic model development.

### Material Assignment

Different regions of the motor were assigned appropriate electromagnetic materials.

These included materials for:

- Copper windings
- Permanent magnets
- Rotor
- Stator
- Shaft
- Air regions

Correct material definition is important because electromagnetic behaviour depends strongly on properties such as conductivity and magnetic permeability.

### Boundary Conditions

Boundary conditions were applied to define how the electromagnetic field interacts with the limits and symmetry regions of the model.

This allowed the reduced 2D motor geometry to represent the behaviour of the larger machine more effectively.

### Mesh Configuration

Mesh operations were configured for important regions of the motor.

The mesh determines how the geometry is divided for numerical electromagnetic analysis. Particular attention is required around areas such as the air gap and magnetic components where the electromagnetic field changes significantly.

### Three-Phase Excitation

The stator windings were assigned electrical excitations representing the three inverter phases.

This allowed the simulation to reproduce the changing current distribution required to generate a rotating magnetic field within the motor.

## Simulation Outputs

Several outputs were analysed to understand the interaction between the inverter and motor.

### Three-Phase Stator Currents

The simulated stator currents show the changing currents in phases A, B and C.

These results demonstrate that the motor is being driven through a three-phase switching sequence rather than a constant electrical supply.

The current behaviour is important because it directly influences:

- Rotating magnetic field generation
- Electromagnetic torque
- Motor efficiency
- Magnetic loading

### Magnetic Flux Density

Transient magnetic flux density was analysed throughout the stator, rotor, permanent magnets and air gap.

This provided insight into how the magnetic field travels through the motor and how the permanent magnets interact with the stator excitation.

The results can also help identify regions where magnetic flux becomes concentrated.

### Magnetic Flux Lines and B-Vector Field

Magnetic flux lines and magnetic field vectors were also investigated.

These visualisations helped demonstrate the direction and distribution of the magnetic field as the three-phase excitation changed during operation.

### Electromagnetic Torque

The transient electromagnetic torque response was calculated to examine how the interaction between the stator field and permanent-magnet rotor produces mechanical torque.

The simulation showed the initial torque build-up followed by a repeating torque response during operation.

## Skills Developed

This project helped me develop practical skills across power electronics, electrical machines and computational modelling.

### Power Electronics

- Three-phase inverter design
- Six-switch bridge topology
- DC-to-AC conversion
- PWM inverter operation
- Switching behaviour analysis
- Modulation index selection
- Switching-frequency analysis

### Electrical Machines

- Permanent-magnet motor operation
- Three-phase stator excitation
- Rotating magnetic fields
- Electromagnetic torque generation
- Motor phase relationships
- Interaction between electrical and magnetic systems

### LTspice

- Building power-electronic simulation circuits
- Parameterised simulation setup
- Creating sinusoidal and triangular control signals
- Implementing PWM switching logic
- Transient simulation
- Phase-voltage analysis
- Line-voltage analysis
- Waveform interpretation
- Debugging simulation behaviour

### ANSYS Maxwell

- 2D electromagnetic modelling
- Transient magnetic analysis
- Material assignment
- Boundary-condition configuration
- Mesh definition
- Coil and winding excitation
- Permanent-magnet modelling
- Magnetic flux-density analysis
- Magnetic flux-line analysis
- B-vector field analysis
- Electromagnetic torque analysis
- Three-phase stator-current analysis

### Engineering Analysis

- Connecting inverter behaviour with motor behaviour
- Interpreting simulation results
- Comparing electrical and electromagnetic outputs
- Understanding model assumptions
- Evaluating the usefulness and limitations of simulation
- Using simulation to investigate a system before physical implementation

## What I Learned

One of the most valuable parts of this project was connecting the theory of three-phase power electronics with the electromagnetic behaviour of an electric motor.

Rather than treating the inverter and motor as completely separate systems, the project demonstrated how inverter switching directly affects the currents supplied to the stator and therefore the magnetic field and torque produced by the motor.

The LTspice model helped me understand how PWM can transform a fixed DC supply into a controllable three-phase output, while the ANSYS Maxwell model demonstrated how three-phase excitation creates changing magnetic fields and electromagnetic torque within a permanent-magnet machine.

The project also gave me experience interpreting engineering simulations rather than simply producing them. This included examining whether phase relationships, switching behaviour, current response, magnetic fields and torque outputs behaved as expected.

## Model Limitations

The simulations are engineering models and therefore include simplifications.

The motor was represented using a 2D quarter-section rather than a complete three-dimensional model. This reduces computational complexity but means that some physical effects present in a real motor are not represented completely.

Similarly, the LTspice inverter provides a controlled simulation of the switching system but does not reproduce every real-world effect that would occur in physical power-electronic hardware.

Potential areas for further development include:

- More detailed semiconductor switching models
- Switching and conduction-loss analysis
- Dead-time implementation
- Thermal modelling
- Higher switching-frequency investigation
- More detailed motor geometry
- Full 3D electromagnetic simulation
- Rotor-speed and load variation
- Closed-loop motor control
- Hardware implementation and experimental validation

## Reflection

The project successfully demonstrated both the electrical and electromagnetic sides of an inverter-driven permanent-magnet motor system.

Building the LTspice inverter made it possible to investigate the generation of three-phase PWM voltages from a DC supply, while the ANSYS Maxwell model provided a way to investigate how electrical excitation produces magnetic flux, stator current behaviour and electromagnetic torque.

If we were to continue the project, we would place greater emphasis on documenting and quantitatively justifying modelling decisions such as mesh density, boundary conditions, switching frequency and simulation parameters. We would also aim to compare the simulation results against experimental measurements from a physical inverter and motor system.

## Tools Used

- LTspice
- ANSYS Maxwell
- Power electronics simulation
- Electromagnetic finite-element modelling
- Transient waveform analysis

## Project Context

This project was completed as part of my Robotics Engineering studies at the University of Bath.

The work was completed collaboratively and contributed to developing my understanding of circuit simulation, computational modelling, power electronics and electric motor-drive systems.
