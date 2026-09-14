# PhysioSentinel Gait · Version 155

## Objetivo
Corrección antirregresión del visor anatómico manteniendo íntegra la exportación maestra de V154.

## Cambios
- Recupera como anatomía prioritaria los huesos Denver registrados y los 76 músculos Denver V11/GeometryPath de V153.
- Con un atlas Denver cargado y validado, el visor ya no puede caer silenciosamente al esqueleto Hamner antiguo de cuerpo completo.
- Si la construcción Denver falla, hace un segundo intento RAM-safe con mallas conectadas.
- Si existe un rig Denver válido del mismo atlas en la sesión, se conserva en vez de sobrescribirlo con `None`.
- Si Denver no puede construirse y no existe un rig válido previo, se muestra error explícito y se bloquea la anatomía regresiva.
- El fallback Hamner se reserva al tren superior cuando Denver está activo; no reemplaza pelvis/miembros inferiores Denver.
- Mantiene piel SKEL completa Opaca/Translúcida, cámara, reproducción, MP4 y Pestañas 12/13.
- Mantiene la exportación maestra de V154 para Pestañas 4,5,9,10,11,12,13 y la malla de piel.
