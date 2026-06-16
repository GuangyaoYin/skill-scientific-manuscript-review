# Geophysics and Seismology Review Checklist

Use this reference for manuscripts on geophysics, seismology, reservoir-induced
seismicity, engineering-related seismicity, tectonic triggering, earthquake
catalogs, source locations, finite-element modeling, poroelasticity,
viscoelasticity, Coulomb stress, pore pressure, and seismic hazard/risk.

## Topic Fit

Pay special attention to manuscripts involving:

- reservoir-induced seismicity;
- fluid injection induced seismicity;
- engineering-activity-related earthquakes;
- tectonic earthquake triggering;
- earthquake catalog analysis;
- high-precision source location;
- double-difference relocation;
- focal mechanisms;
- b-value analysis;
- Coulomb stress calculation;
- pore-pressure diffusion;
- poroelastic or viscoelastic modeling;
- thermo-hydro-mechanical coupling;
- finite-element numerical modeling;
- seismic hazard or risk inference.

## Earthquake Catalog and Seismicity Data

Check:

- catalog completeness and magnitude of completeness Mc;
- station distribution and network changes;
- phase picking quality;
- velocity model and location method;
- horizontal and depth uncertainty;
- reliability of focal depths;
- relocation method and parameters;
- magnitude consistency;
- b-value calculation method and uncertainty;
- whether apparent spatiotemporal migration could reflect detection capability;
- criteria for classifying artificial, induced, triggered, natural, or
  anthropogenic-related events;
- completeness and timing of engineering data such as water level, injection
  rate, excavation, blasting, construction schedule, or reservoir operation.

## Figures for Seismology Papers

Check:

- hypocenter distribution is not merely controlled by network geometry;
- depth sections are credible and show uncertainties when needed;
- magnitude-frequency plots report Mc;
- b-value maps include error or sample-count information;
- focal mechanism plots have enough samples;
- fault projections and cross-sections are geometrically justified;
- time series of water level, injection, pore pressure, seismicity rate, or event
  magnitude use consistent time axes;
- maps include scale, north arrow, coordinates, regional location, faults,
  stations, and event symbols.

## Induced or Triggered Seismicity Causality

Do not accept an induced-seismicity claim based only on time or space correlation.
Check the full chain:

1. the engineering or natural disturbance is documented;
2. disturbance timing precedes the seismic response;
3. source-region distance and geometry are plausible;
4. pore pressure, poroelastic stress, Coulomb stress, or other perturbation can
   reach the source region;
5. perturbation magnitude is physically meaningful relative to fault stability;
6. seismicity migration, rate changes, focal mechanisms, or b-value patterns are
   consistent with the proposed mechanism;
7. natural tectonic background is evaluated;
8. alternative mechanisms are discussed;
9. terminology distinguishes `induced`, `triggered`, `natural`, and
   `anthropogenic-related`.

Flag hazard or risk claims when they exceed the evidence.

## Numerical and Finite-Element Modeling

Check:

- governing equations are clear;
- boundary and initial conditions are justified;
- material parameters have literature or measurement support;
- mesh resolution is adequate and convergence is tested;
- time step is stable and appropriate;
- fault geometry is reliable;
- receiver fault parameters are justified;
- friction, Skempton coefficient, permeability, viscosity, diffusivity, elastic
  constants, pore-pressure parameters, and key coupling coefficients are justified;
- stress, pore pressure, displacement, strain, and other outputs have credible
  magnitudes and units;
- model outputs are compared with observations;
- physical assumptions are distinguished: elastic, poroelastic, viscoelastic,
  thermoelastic, hydro-mechanical, or coupled;
- the model is not overcomplicated relative to validation evidence.

## Reviewer Comment Patterns

Use comments like these when supported by the manuscript:

```text
The manuscript interprets the temporal correspondence between [engineering activity] and [seismicity response] as evidence for triggering. However, the causal chain is not fully demonstrated. The authors should quantify the stress or pore-pressure perturbation at the source region, evaluate whether its magnitude is sufficient to affect fault stability, and compare this mechanism with plausible tectonic background activity.
```

```text
The earthquake catalog analysis requires a clearer assessment of catalog completeness and location uncertainty. Without Mc, station-coverage information, and relocation-error estimates, it is difficult to determine whether the reported spatiotemporal migration reflects physical evolution or changes in detection capability.
```

```text
The numerical model would be more convincing if the authors reported mesh-convergence tests, parameter sensitivity tests, and an uncertainty range for the modeled stress or pore-pressure perturbations. These checks are important because the main conclusion depends on the magnitude and spatial distribution of the modeled perturbation.
```
