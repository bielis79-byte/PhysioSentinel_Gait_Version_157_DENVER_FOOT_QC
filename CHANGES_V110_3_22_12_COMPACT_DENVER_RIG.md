# V110.3.22.12 · Compact Denver Rig / RAM-safe

Causa abordada: el log de V110.3.22.10 muestra que Streamlit arrancó y funcionó,
pero finalmente /healthz devolvió EOF sin traceback Python. La nueva arquitectura
reduce drásticamente la memoria del visor anatómico.

## Cambio principal
ANTES:
- huesos Denver: vertices[75, N, 3]
- músculos Denver: vertices[75, M, 3]
- Hamner completo además podía construirse antes del Denver.

AHORA:
- una sola malla ósea Denver frame 1;
- una sola malla muscular Denver frame 1;
- 8 transformaciones segmentarias compactas por frame;
- bounded-skinning calculado en el navegador a partir de pesos por vértice;
- Hamner completo solo se crea si Denver falla;
- en modo Denver solo se conserva la pequeña geometría superior Hamner.

## Memoria
Se eliminan de session_state las matrices Denver de 75 frames.
La app guarda geometría base + caras + pesos + matrices 3x3/traslación.

## Geometría
- simplificación conectada;
- fallback puro numpy por vertex clustering si no hay decimador;
- huesos rígidos;
- músculos con bounded skinning proximal/distal.

## Video
La reconstrucción compacta se usa tanto en reproducción como en exportación MP4,
por lo que el vídeo conserva el mismo modelo que aparece en pantalla.
