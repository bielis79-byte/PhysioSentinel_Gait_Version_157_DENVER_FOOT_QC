# V110.3.22.11 · Cloud-safe Denver anatomy

Motivo:
V110.3.22.10 muestra `Oh no. Error running app` antes de abrir la interfaz.
Eso indica un fallo de arranque/deploy, no un problema visual del visor.

Corrección preventiva:
- se elimina `fast-simplification` de requirements;
- no se añade ninguna dependencia binaria nueva al arranque de Streamlit Cloud;
- la simplificación intenta usar el backend disponible de trimesh;
- si no existe, conserva la malla STL completa y conectada;
- nunca vuelve a F[::step] ni a triángulos aislados.

Se mantienen:
- build_visible_human_bone_sequence restaurado;
- build_denver_bone_master restaurado;
- bounded skinning muscular;
- huesos Denver visibles;
- músculos Denver volumétricos;
- OpenSim/SKEL como rig interno;
- caché nueva V110.3.22.11.

Nota:
Si esta versión también falla antes de mostrar la UI, hace falta el traceback de
Manage app > Logs, porque la pantalla genérica de Streamlit no contiene la causa.
