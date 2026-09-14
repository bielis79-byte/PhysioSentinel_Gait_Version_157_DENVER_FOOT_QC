# PhysioSentinel Gait · Versión 151

## Pestaña 12 · Cinemática Anatómica 3D
Se conservan curvas articulares, ROM, velocidad, aceleración, simetría, coordinación intersegmentaria, diagramas ángulo–ángulo, trayectorias 3D y suavidad.

Se añaden:
- variabilidad cinemática intrasecuencia (SD angular, SD de Δ/frame y RMS de Δ/frame), con advertencia explícita de que la variabilidad ciclo-a-ciclo requiere varios ciclos individualizados;
- índices derivados transparentes: Simetría Cinemática 3D, Coordinación Intersegmentaria, Suavidad Cinemática y Variabilidad Intrasecuencia;
- exportación completa de tablas y gráfico global a la Pestaña 8.

## Pestaña 13 · Análisis Musculoesquelético 3D
Usa el rig muscular Denver + GeometryPath de la variante Hamner cargada + retarget jerárquico SKEL + RMF.

Incluye:
- selector de músculo y lado;
- GeometryPath 3D por frame;
- longitud musculotendinosa geométrica LMT;
- ΔL respecto a media del ciclo o frame 1;
- velocidad geométrica de elongación/acortamiento;
- excursión absoluta y relativa;
- fase de longitud mínima y máxima;
- simetría musculotendinosa bilateral;
- diagramas ángulo–longitud según articulaciones relacionadas;
- coordinación entre grupos musculares, correlación y mejor desfase temporal ±15 frames;
- resumen de los 76 músculos y manifiesto de mapping GeometryPath.

La velocidad se expresa en unidades SKEL/s solo cuando el objeto SKEL aporta una duración física fiable; en caso contrario se mantiene en unidades SKEL/frame.

## Pestaña 8 · Exportar / Descargar
El ZIP global se amplía a Pestañas 10/11/12/13. Exporta todos los resultados numéricos de Pestañas 12 y 13, no solo el músculo o gráfico actualmente seleccionado, además de las gráficas renderizadas y vídeos ya disponibles.

## Alcance
No se infiere fuerza muscular, activación EMG, momentos articulares, potencia muscular, GRF ni carga articular real.
