# Version 157

Version 157 is based on Version 156 and keeps its restored Export tab, master export, NPZ standalone mode, Denver anatomy and musculoskeletal analysis.

The change is deliberately distal and guarded: Denver foot anatomy receives the internally validated local roll correction around Heel-to-Toe, while the original SKEL motion remains unchanged. A new foot/ankle QC layer grades distal geometry, temporal continuity, talus-calcaneus-toes coherence, an auxiliary 3D contact hint and inversion/eversion reliability.

Legacy NPZ files remain supported. If they do not contain detector confidences, PhysioSentinel labels confidence as geometric rather than pretending that a detector score exists.
