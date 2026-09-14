# PhysioSentinel Gait · Version 152

## Corrección principal

Se corrige el puente de estado entre **Pestaña 11 · Atlas anatómico 3D** y **Pestaña 13 · Análisis Musculoesquelético 3D**.

### Problema de V151
La Pestaña 13 se evaluaba antes que el bloque que construía/publicaba el rig Denver-Hamner de la Pestaña 11. En el primer ciclo de ejecución podía mostrar el aviso de que faltaba el atlas aunque NPZ SKEL y Denver estuvieran ya cargados y visibles en la Pestaña 11.

### Solución V152
- Nuevo alias persistente `v152_denver_muscle_rig`.
- Nuevo descriptor `v152_musculoskeletal_bridge` con estado, rig, secuencia, frames y SHA del atlas.
- Compatibilidad con la clave histórica `v149_denver_muscle_rig`.
- Al construir el rig por primera vez, se realiza **un único `st.rerun()` controlado por cache_key** para que la Pestaña 13 lo vea inmediatamente en el mismo flujo de sesión.
- Al cambiar de atlas Denver se invalidan también las nuevas claves V152.
- La Pestaña 13 diferencia ahora entre: secuencia SKEL presente pero rig aún no publicado, y ausencia real de datos.
- No se regeneran los 75 frames SKEL.
- Se mantiene intacta la exportación completa de las Pestañas 12 y 13 hacia la Pestaña 8.

## No modificado
Piel opaca/translúcida, malla SKEL, 75 frames, Denver bones, Denver V11 muscle volume, GeometryPath Hamner, cámara libre, reproducción y exportación de vídeo.
