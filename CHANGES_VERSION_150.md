# PhysioSentinel Gait · Versión 150

## Corrección de Piel Opaca

- La piel SKEL del visor integrado deja de usar muestreo de caras `F[::step]`.
- Se envía al navegador la topología completa y conectada de la malla SKEL en los 75 frames.
- **Opaca** usa `opacity=1` sobre la misma superficie continua.
- **Translúcida** usa `opacity=0.24` sobre exactamente la misma topología.
- `flatshading=False` y material/iluminación suave para evitar la apariencia facetada.
- Se mantienen sin cambios: 75 frames, SEGMENT GENTLE, huesos Denver, motor muscular V11, cámara manual, reproducción y exportación MP4 exacta.
- No se vuelve a ejecutar SKEL ni se modifica la cinemática.

## Motivo

La Versión 149 reducía el payload de piel tomando cada N-ésima cara. Eso conservaba vértices pero rompía visualmente la continuidad de la superficie y producía islas triangulares. La Versión 150 elimina esa reducción únicamente para la piel final del visor.
