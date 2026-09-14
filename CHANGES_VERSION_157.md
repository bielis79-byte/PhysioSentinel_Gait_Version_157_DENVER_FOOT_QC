# PhysioSentinel Gait · Version 157

## Denver lower-limb / foot orientation
- Corrects the Denver foot donor frame by a 180-degree roll around the anatomical Heel-to-Toe longitudinal axis.
- The correction flips only the donor local transverse/dorso-plantar axes; it preserves Heel-to-Toe progression, SKEL q(t), joints, skin vertices, thigh and shank kinematics.
- Denver bone-master cache key was bumped so an old cached donor frame cannot silently preserve the previous orientation.

## Foot/ankle quality control
- Adds geometric Heel/Toe confidence when detector-level confidence is unavailable in legacy NPZ files.
- Adds temporal continuity QC for ankle q(t) and Heel-to-Toe orientation.
- Adds talus-calcaneus-toes chain coherence QC.
- Adds a 3D contact hint using distal height + vertical speed. It is explicitly auxiliary and never replaces IC/TO 2D, footswitch or force-plate data.
- Adds inversion/eversion reliability gating from subtalar dynamic information and distal geometry. Low-information recordings are labeled `Orientativo · baja fiabilidad`.
- Future NPZs can preserve optional detector-level foot landmark scores when present.

## Tab 12 / Export
- New Foot/Ankle QC table in Cinematica Anatomica 3D.
- New exports: `09_control_calidad_pie_tobillo.csv` and `10_control_calidad_pie_tobillo.json`.

## Methodological safeguards
- No global 180-degree lower-limb rotation is applied.
- No new smoothing modifies the 75-frame sequence.
- No force, EMG, moment or GRF inference is added.
