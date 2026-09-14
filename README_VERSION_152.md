# PhysioSentinel Gait Version 152

Versión de mantenimiento centrada en la comunicación de estado entre el visor anatómico de la Pestaña 11 y el análisis musculoesquelético de la Pestaña 13.

Flujo esperado:
1. Reabrir/generar NPZ SKEL de 75 frames.
2. Cargar atlas Denver compatible.
3. La Pestaña 11 construye o recupera el rig muscular compacto.
4. V152 publica el rig en `session_state` y, cuando es necesario, fuerza un único refresco controlado.
5. La Pestaña 13 reutiliza el rig sin fitting ni regeneración de los 75 frames.

Los resultados musculotendinosos siguen siendo geométricos/cinemáticos del modelo. No representan EMG, fuerza muscular, momentos articulares ni GRF.
