# PhysioSentinel Gait · Versión 153

## Cambios principales

1. **Pestaña 13 → session_state persistente**
   - Publica `v153_tab13_results` y `v153_tab13_exports`.
   - Conserva resumen de 76 músculos, 38 pares bilaterales y 21 comparaciones de coordinación, además de series completas.
   - Un único `st.rerun()` controlado garantiza que la Pestaña 8 vea los resultados aunque se renderice antes que la Pestaña 13.

2. **Pestaña 8 incorpora automáticamente la Pestaña 13**
   - `musculos_resumen_76.csv`
   - `simetria_musculotendinosa_38.csv`
   - `coordinacion_muscular_21.csv`
   - `series_LMT_DeltaL_vMT_76_musculos.csv`
   - `diagramas_angulo_longitud_todos_musculos.csv`
   - `curvas_coordinacion_grupos_musculares.csv`
   - `manifest_geometrypath_muscular.csv`
   - Mantiene además las figuras PNG generadas por la Pestaña 13.

3. **Nombres de archivo semánticos**
   - Se eliminan del bloque persistente los prefijos antiguos `01_...05_` para facilitar informes automáticos.

4. **Tronco: inclinación ≠ traslación ≠ COM**
   - Añadida traslación mediolateral centro de hombros respecto al centro pélvico.
   - Normalización por anchura pélvica (%).
   - Añadida posición del centro torácico respecto al punto medio de la BOS, normalizada por media base (`ratio`; 0=centro, |1|≈centro de un pie).
   - Se mantiene separada la inclinación angular del tronco y el COM proxy.
   - Se normaliza el signo a derecha/izquierda anatómica cuando la orientación frontal/posterior está definida; si no, se conserva coordenada de imagen.
   - Añadidos resumen robusto P95, media firmada y consistencia cíclica.

5. **Exportación frontal específica**
   - `biomecanica_frontal/tronco_pelvis_COM_BOS_series.csv`
   - `biomecanica_frontal/tronco_pelvis_COM_BOS_resumen.csv`

## No modificado
No se modifica fitting SKEL, 75 frames, GeometryPath Hamner, mallas Denver, cámara, piel, reproducción ni exportación de vídeo. No se infieren fuerza muscular, EMG, momentos articulares ni GRF.
