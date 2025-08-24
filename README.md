![FluidDemo](https://github.com/user-attachments/assets/2c77dc8f-4bd2-45b5-8206-0fe80290ac82)

# A C++ port of Ten Minute Physics FLIP demo by Matthias Müller with added features

Original demo / video: https://matthias-research.github.io/pages/tenMinutePhysics/

A C++ port of Matthias Müller's JavaScript FLIP (Fluid-Implicit-Particle) fluid simulation demo using OpenGL for rendering.

## What is FLIP?

FLIP (Fluid-Implicit-Particle) is a hybrid fluid simulation method that combines the best aspects of grid-based and particle-based approaches:

- **Grid-based velocity**: Uses a regular grid (MAC grid) to solve incompressible fluid equations efficiently
- **Particle-based advection**: Particles carry velocity and other properties, avoiding numerical diffusion
- **Hybrid transfer**: Velocities are transferred between particles and grid each timestep using interpolation
- **PIC/FLIP blending**: Combines PIC (Particle-in-Cell) for stability and FLIP for detail preservation

This approach provides:
- **Incompressibility**: Proper pressure solve ensures volume conservation
- **Detail preservation**: Particles maintain fine-scale motion and vorticity
- **Stability**: Grid-based solve prevents particle clustering issues
- **Efficiency**: Faster than pure particle methods for large simulations

The simulation pipeline: integrate particles → separate particles → handle collisions → transfer to grid → solve pressure → transfer back to particles.

## Features

- FLIP/PIC fluid simulation with hybrid particle-grid method
- Interactive obstacle manipulation with mouse drag
- Real-time particle and grid visualization with color mapping
- Adjustable simulation parameters via ImGui interface
- 2D gravity vector control (X and Y components)
- Particle separation and collision handling
- Density-based drift compensation
- Cross-platform support (Linux, macOS, Windows)
- Theoretically works out the box (not sure about macOS)

## License

- MIT License (same as original JavaScript version)
