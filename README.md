# SortIQ Parts Sorter

**Status:** In progress  
**Expected completion:** December 29, 2026

SortIQ is a camera-assisted tabletop sorter. The system architecture is still being refined; this repository will document the selected design, interfaces, and measured behavior as they are implemented.

## Architecture under development

- Camera and Raspberry Pi 5 for visual input and classification are proposed.
- Rust is being explored for the vision/control application; computer-vision workflow and language split are still being finalized.
- A TM4C123 LaunchPad is proposed for deterministic sensor and actuator control, with a UART link under consideration.
- A PCA9685 board and standard hobby servo are available for a feeder gate/flap.
- The Hiwonder xArm uses its own smart-servo controller; do not assume the PCA9685 directly controls the arm.

## Goals (not measured results)

- Target at least 95% classification accuracy on a documented test set.
- Target less than 8 seconds per item, measured from the defined start/end events.
- Verify safe, repeatable feeder and pick-and-place sequencing.

These are goals, not current results. Record the item categories, lighting/camera setup, sample count, confusion matrix, timing definition, and failed picks before reporting performance.

## Repository structure

```text
vision/         Camera capture and classification
embedded/       TM4C123 firmware and interface
mechanism/      Feeder, xArm setup, and CAD/wiring references
docs/           System architecture, interface contract, and validation log
```

Keep controller responsibilities, connector pinouts, voltage levels, and servo power requirements in the documentation as the design is finalized.
