# V110.3.22.13 · Denver Landmark Registration

Corrección del problema visual de V110.3.22.12: huesos y músculos no proporcionados/alineados.

Hallazgos:
1. El clasificador antiguo interpretaba cartílagos como huesos porque buscaba
   palabras como 'femur' antes de comprobar el tipo de STL.
   Resultado observado: 46 'huesos' en vez de los 28 reales.
2. Los nombres musculares Denver están en CamelCase y el normalizador antiguo
   no los separaba correctamente.
   Resultado observado: 37 músculos detectados en vez de ~76.
3. Los frames donantes se obtenían por PCA de huesos aislados. Esto no garantiza
   que el eje anatómico Denver coincida con cadera-rodilla-tobillo/pie.

V110.3.22.13:
- clasifica únicamente STL _Bone_ como hueso y _Muscle_ como músculo;
- ignora cartílago/ligamento como geometría visible;
- conserva cartílago como LANDMARK para el registro;
- fuerza reconstrucción del manifest con schema_version=3;
- obtiene centros articulares Denver de:
  * Cartilage_FemurHead
  * Cartilage_FemurDistal
  * Cartilage_TibiaDistal
  * Bone_Calcaneous
  * Bone_Phalanges
- reemplaza PCA por frames anatómicos explícitos;
- alinea pelvis/cadera, fémur, tibia y pie con los joints SKEL correspondientes;
- corrige el frame del pie para usar tobillo como origen y talón→dedos como eje;
- invalida caches antiguos de atlas/malla;
- mantiene el rig compacto RAM-safe y bounded skinning.

Objetivo:
Denver define la morfología visible; SKEL/OpenSim define la cinemática.

## Corrección específica tras la validación con el ZIP Female real

La prueba automática detectó 26/28 huesos y 74/76 músculos.

Los cuatro STL omitidos eran:
- VHF_Left_Bone_Calcaneous_smooth.stl
- VHF_Right_Bone_Calcaneous_smooth.stl
- VHF_Left_Muscle_Illiacus_smooth.stl
- VHF_Right_Muscle_Illiacus_smooth.stl

Causa:
- Denver usa `Calcaneous` mientras el nombre anatómico canónico es `calcaneus`.
- Denver usa `Illiacus` mientras el canónico es `iliacus`.

Esto explicaba directamente:
- pie/tobillo incompleto: faltaba el calcáneo;
- región de cadera incompleta: faltaba el iliaco.

Se añaden ambos alias y la validación exige ahora exactamente 28 huesos y 76 músculos.
