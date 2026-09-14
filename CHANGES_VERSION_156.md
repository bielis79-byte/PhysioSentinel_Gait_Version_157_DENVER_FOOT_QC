# PhysioSentinel Gait · Version 156

## Corrección crítica
- Restaurada la Pestaña 8 · Exportar / Descargar, que había quedado sin bloque `with tabs[7]:` en V155.
- Recuperados los botones de descarga individual y el botón principal **📦 Descargar TODO en ZIP**.
- La exportación maestra sigue llamando al constructor existente `build_export_zip()` y conserva la agregación de Pestañas 4, 5, 9, 10, 11, 12 y 13.
- Se mantiene la exportación de la malla SKEL completa de piel de 75 frames (`piel_SKEL_75frames_opaca_translucida.npz`) cuando está disponible en sesión.
- No se modifica la anatomía Denver, el rig muscular V11, GeometryPath Hamner, cámara, visor 3D ni cinemática.

## Validación
- `streamlit_app.py` compila correctamente.
- Existe exactamente un bloque `with tabs[7]:` y un bloque `with tabs[8]:`.
- El botón `📦 Descargar TODO en ZIP` vuelve a estar presente en el flujo de la interfaz.
