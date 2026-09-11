# Soft Body Blob

A single-file browser soft-body experiment with accumulated damage, partial healing, cascading fracture, independently simulated fragments, self-collision, and stress-linked material rendering.

## Run

Open `index.html` in a WebGL2 browser. There is no build step, package install, server, or network dependency.

**Drag** to deform the body · **pull harder** to damage and tear it · **release** to let subcritical damage recover · **R** or **reset** rebuilds it.

## Implementation

- A fixed 180 Hz particle simulation with compliant distance constraints and iterative solving.
- Different shell, interior, cross-brace, and long-range constraints give the body nonuniform stiffness and redundant structure.
- Overstrain accumulates damage instead of causing an immediate binary cut. Damage below failure slowly recovers when the load is removed.
- Broken constraints redistribute load through the remaining structure, allowing cracks and cascading failure without preset tear lines.
- Detached connected components remain fully simulated and continue deforming, colliding, and interacting with the floor and one another.
- A spatial self-collision pass reduces particle interpenetration as the body folds or compresses.
- The WebGL material couples deformation back into appearance with refraction, Fresnel reflection, thickness cues, stress-linked roughness, and soft contact shadowing.

The simulation is an interactive real-time approximation, not a validated continuum, molecular, or finite-element material model.

## License

[MIT](LICENSE)
