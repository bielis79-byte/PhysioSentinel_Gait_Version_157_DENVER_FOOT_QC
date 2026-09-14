# PhysioSentinel Gait · Version 154

## Exportacion maestra unificada
- Un unico ZIP principal desde Pestaña 8 para Pestañas 4, 5, 9, 10, 11, 12 y 13.
- Pestaña 4: métricas 2D y datos fuente de gráficos.
- Pestaña 5: histórico/evolución disponible en la sesión y sesiones del paciente.
- Pestaña 9: ciclo, fases y cinemática angular V90.
- Pestaña 10: capacidad locomotora, perfil biomecánico, dominios y prioridades.
- Pestaña 11: malla SKEL completa de 75 frames usada por Piel Opaca/Translúcida, joints/poses cuando están disponibles y manifiesto del rig.
- Pestaña 12: todas las salidas publicadas por Cinemática Anatómica 3D.
- Pestaña 13: todos los CSV musculotendinosos semánticos, curvas, diagramas y figuras disponibles.

## Piel opaca
La piel opaca y translúcida son la misma malla SKEL conectada. El ZIP incluye `P11_Atlas_Anatomico_3D/piel_SKEL_75frames_opaca_translucida.npz` con vertices, faces y, cuando existen, joints y poses. El manifiesto documenta opacity 1.0 para Opaca y 0.24 para Translúcida.

## Nota sobre vídeo del visor
El vídeo exacto "tal como se ve" continúa generándose en el navegador WebGL. V154 incluye la malla 75F reproducible en el ZIP maestro, pero no incorpora automáticamente esa captura de cámara al ZIP del servidor hasta que el navegador la devuelva a Streamlit.
