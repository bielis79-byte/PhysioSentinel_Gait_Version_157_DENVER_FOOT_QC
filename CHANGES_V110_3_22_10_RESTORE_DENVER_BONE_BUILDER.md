# V110.3.22.10 · Restore Denver Bone Builder

## Causa real del fallo de V110.3.22.9
Al sustituir el algoritmo muscular por bounded skinning, el archivo
`visible_human_atlas.py` fue truncado a partir de
`build_visible_human_muscle_sequence`.

Como consecuencia desaparecieron accidentalmente:
- `_bone_segment`
- `build_denver_bone_master`
- `_register_denver_bones_frame0`
- `build_visible_human_bone_sequence`

Por eso Streamlit mostraba:
`ImportError: cannot import name 'build_visible_human_bone_sequence'`
y activaba inmediatamente el fallback Hamner.

## Corrección
- se restauran las funciones de hueso Denver;
- se conserva el bounded skinning muscular validado;
- las mallas óseas restauradas usan `_simplify_connected_mesh`, no F[::step];
- se incrementa la clave de caché a V110.3.22.10;
- no se reutiliza el fallback roto de V22.9.

## Arquitectura esperada
- piel: SKEL;
- huesos visibles pelvis/miembro inferior: Denver;
- músculos visibles: Denver;
- OpenSim/Hamner: rig interno;
- Hamner visible solo como fallback superior.
