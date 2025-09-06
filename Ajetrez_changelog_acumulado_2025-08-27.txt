Ajetrez — Changelog acumulado (hasta 2025-08-27)
Versión estable actual: “ajetrez ver 2.2 estable”

======================================================================
2025-08-27 — ver 2.2 estable
----------------------------------------------------------------------
1) Carteles/avisos del bot (reintroducidos y mejorados)
   • Flujo de turnos:
     - Tras el movimiento humano: espera de 1 segundo.
     - Cartel ~3 s anunciando la jugada del bot (“El bot ha decidido mover {pieza} a {casilla}”).
     - Al desaparecer el cartel, el bot ejecuta la jugada.
     - Si hubo captura:
       · Cartel ~3 s: “El bot está decidiendo si mantener o desplazar la sección.”
       · Cartel ~3 s: “El bot decide mantener la sección.” o “El bot decide desplazar la sección.”
       · La acción (mantener/desplazar) ocurre solo después de que desaparece este segundo cartel.
   • Ralentización general para mayor legibilidad.
   • Anti-reentrada: el bot no actúa dos veces mientras hay carteles en pantalla.
   • Respeto de reglas: si desplazar la sección no es legal, el bot mantiene.
   • Estilo/posición del cartel:
     - Cartel compacto (tipografía más pequeña, padding reducido).
     - Aparece centrado en la parte superior del tablero.
     - Elevado medio casillero por encima del borde superior.
     - Se reubica en scroll/resize (anclado a #board / #mobile-board-down-1square).

2) Modo de juego (UI y comportamiento)
   • El juego inicia por defecto en “vs Bot”; “1v1 local” queda como segunda opción.
   • Se reemplaza el selector por indicador + botón de alternancia:
     - Indicador tipo “pill” negro con texto blanco: “Estás en modo: <vs Bot / 1v1 local>”.
     - A la derecha del botón existente en la barra superior.
     - Botón único “Cambiar a …” para alternar de modo (reset limpio al cambiar).
   • Aplicado en versiones web y móvil.

3) Versionado
   • Nombrada como versión estable: “ajetrez ver 2.2 estable”.

======================================================================
2025-08-18 — referencias de base (UI botones/posicionamiento)
----------------------------------------------------------------------
• Botones transparentes (solo texto), inicialmente en negro y luego en rojo; tamaños ajustados (+10%).
• En móvil:
  - Desplazamiento del control +2 casilleros a la derecha (luego +4 en total).
  - Offset vertical mantenido (-11 casilleros aprox.).
  - Ajustes replicados en fullscreen móvil.
• En PC (normal y fullscreen):
  - Desplazamiento del control +2 casilleros a la derecha (con alzado previo de −10 px − 1.5×casillero).
  - Offsets de móvil respetados cuando corresponden.
• Archivos de referencia y estados marcados en la fecha:
  - “ajetrez_stable_2025-08-18_mobile_pcfs.html”: base para móvil y PC en pantalla completa.
  - “ajetrez_web_fs_right5_REVERT_2025-08-18.html”: señalada como última versión estable de escritorio sin desplazamiento vertical del botón FS y ajustes previos aplicados.

======================================================================
Notas
----------------------------------------------------------------------
• Todos los cambios del 27-08-2025 se integraron en un único archivo HTML final, manteniendo compatibilidad con web y móvil.
• Recomendación para despliegue: usar el archivo sin espacios en el nombre para enlaces (Netlify/URLs): “ajetrez_ver_2_2_estable.html”.
• Si hace falta, se puede exponer un parámetro global de tiempos (p. ej., “preBannerDelay”) para ajustar fácilmente la espera de 1 s sin tocar el código.
