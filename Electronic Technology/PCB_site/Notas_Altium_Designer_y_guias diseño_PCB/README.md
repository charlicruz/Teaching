# Notas de Altium Designer y directrices para el diseño de PCB

Guía práctica para diseñar una PCB estándar con **Altium Designer**.  
<br />**Este documento se encuentra actualmente en desarrollo.**

<p align="center"> 
<img src="https://www.altium.com/altium-designer-coming-soon/theme/images/AD_FirstScreen_X2_black.png">
</p>

## Índice de contenidos
- Información general
- [Atajos de teclado](#atajos-de-teclado)
- Componentes
- [Esquemáticos](#esquemáticos)
- [Configuración previa al layout](#configuración-previa-al-layout)
  - [Reglas](#reglas)
  - [Stackup](#stackup)
  - [Configuración de colores de red](#configuración-de-colores-de-red)
- [Colocación de componentes](#colocación-de-componentes)
- Layout
- Recomendaciones para alta velocidad
- [Enlaces útiles](#enlaces-útiles)

---

## Atajos de teclado

Atajos completos de Altium Designer [[Descargar](http://valhalla.altium.com/Learning-Guides/Legacy/GU0104%20Shortcut%20Keys.PDF)]  
<br />Más de 400 atajos para Altium Designer [[Ver](https://shortcutworld.com/Altium-Designer/win/Altium-Designer_Shortcuts)]

### Editor de esquemáticos

#### General
- `Ctrl` + `M`: Medir.
- `C` y después `C`: Compilar el proyecto activo.
- `D` y después `U`: Actualizar la PCB con los cambios del esquemático.
- `D` y después `O`: Abrir la ventana **Document Options**.
- `Q`: Alternar entre unidades métricas e imperiales.
- `T` y después `C`: Hacer *cross-probe* de una red, pin o componente entre el esquemático y la PCB.

#### Cableado del esquemático
- `P` y después `W`: Comenzar a colocar cables.

#### Colocación de componentes
- `J` y después `C`: Ir a un componente.
- `J` y después `N`: Ir a una red.
- `T` y después `A` y después `A`: Abrir la ventana **Annotate**.
- `T` y después `A` y después `U`: Abrir la ventana **Quick Annotate**.

### Editor de PCB

#### General
- `D` y después `I`: Importar cambios desde el esquemático a la PCB.
- `T` y después `D` y después `R`: Ejecutar el DRC (*Design Rule Check*).
- `Q`: Alternar entre unidades métricas e imperiales.
- `T` y después `C`: Hacer *cross-probe* de una red, pin o componente entre el esquemático y la PCB.

#### Ruteado
- `P` y después `T`: Iniciar el ruteado de una pista.
- `Tab` (durante el ruteado): Abrir la ventana de opciones o propiedades de ruteado.
- `Shift` + `Space`: Cambiar el estilo de ruteado de la pista.
- `Shift` + `W`: Seleccionar el ancho de pista desde la lista predefinida.
- `T` y después `G` y después `A`: Rellenar de nuevo todos los polígonos.

#### Colocación de componentes
- `L`: Voltear un componente.
- `Barra espaciadora`: Rotar un objeto 90°.
- `J` y después `C`: Ir a un componente.
- `Ctrl` + `Shift` + `C`: Alinear centros horizontalmente.
- `Ctrl` + `Shift` + `T`: Alinear bordes superiores.
- `Ctrl` + `Shift` + `B`: Alinear bordes inferiores.
- `Ctrl` + `Shift` + `V`: Alinear centros verticalmente.
- `Ctrl` + `Shift` + `L`: Alinear a la izquierda.
- `Ctrl` + `Shift` + `R`: Alinear a la derecha.
- `E` y después `M` y después `M`: Mover un componente.

#### Visualización
- `Shift` + `S`: Ocultar todas las capas excepto la seleccionada.
- `V` y después `B`: Girar la placa.
- `MouseScroll`: Desplazamiento arriba/abajo.
- `Shift` + `MouseScroll`: Desplazamiento izquierda/derecha.
- `Ctrl` + `MouseScroll`: Zoom.
- `Ctrl` + `M`: Medir.
- `+` / `-`: Recorrer las capas habilitadas.
- `*`: Recorrer únicamente las capas de ruteado.
- `S` y después `S` / `Ctrl` + `H`: Seleccionar una sección de cobre conectada.
- `D` y después `T` y después `<letra>`: Seleccionar una configuración de vista.
  - `D` y después `T` y después `U`: Selecciona la configuración superior.
  - `D` y después `T` y después `D`: Selecciona la configuración inferior.
- `D` y después `O`: Abrir la ventana **Board Options**.
- `Ctrl` + `G`: Abrir el editor de rejilla.
- `L`: Mostrar el cuadro de diálogo de capas para ajustar visibilidad y activación.
- `G`: Alternar entre las rejillas predefinidas.

---

## Esquemáticos

- Dibujar los circuitos de **izquierda a derecha** y de **arriba a abajo**.
- Organizar el diseño en bloques funcionales y usar **Net Labels** para conectar bloques entre sí.
- Utilizar **designadores estándar**:
  - Circuito integrado: `IC` o `U`
  - Resistencia: `R`
  - Condensador: `C`
  - Inductor: `L`
  - Transistor: `Q` o `T`
  - Diodo o LED: `D`
  - Cristal: `Y` / `XTAL`
  - Conectores de pines: `J`
  - Jumper: `JP`
  - Fusible: `F`
  - Ferrita: `FB`
  - Fiducial: `FD`
  - Punto de prueba: `TP`

- Añadir una **portada** al esquemático con:
  - Nombre del proyecto
  - Fecha
  - Número de revisión o versión
  - Nombres de todos los esquemáticos
  - Leyenda de notas
  - Información de la empresa
  - Estado del esquemático con fecha:
    - **Borrador**: estructura general del esquemático
    - **Preliminar**: conexiones realizadas, próximo a la versión final
    - **Revisado**: esquemático sin errores
    - **Liberado**: PCB enviada a fabricación

- No conectar cuatro cables en una misma unión.
- Colocar etiquetas, designadores, pines y textos **horizontalmente** siempre que sea posible.
- **No saturar** toda la hoja.
- Nombrar los esquemáticos con nombres **claros** y **breves**.
  - Por ejemplo: `CPU_HDMI` y `CPU_LVDS` en lugar de `CPU1` y `CPU2`.
- Usar nombres del tipo `+...V...` para las redes de alimentación.
  - **No usar nunca `VCC` como nombre de red.**
  - Por ejemplo: `+12V`, `+5V`, `+3V3`, `+2V5`.
- Rellenar la información del bloque de título.
- Utilizar nombres **claros y diferenciados** para los distintos esquemáticos.
- Añadir **notas de diseño** útiles cuando sea necesario.
- Si sospechas que un componente puede ser necesario, inclúyelo inicialmente; siempre podrá eliminarse más adelante.
- **Comprobar cuidadosamente** las líneas RX y TX.
  - **No usar `TX` y `RX` solos como nombre de red.**
  - Por ejemplo: `MCU_TX` o `GPS_RX`.
- Añadir suficientes **puntos de prueba (TP)** para facilitar la depuración.
- Colocar en el esquemático los componentes **próximos a los pines** donde deberán ir en la PCB.
  - Por ejemplo: los condensadores de desacoplo.
- Generar un **PDF** del esquemático final.

---

## Configuración previa al layout

### Reglas

#### Separación
- `D` y después `R` > `Design Rules` > `Electrical` > `Clearance`
- **Clearance** = `0.2 mm`

#### Ruteado
- `D` y después `R` > `Design Rules` > `Routing` > `Width`
- Anchura mínima = `0.254 mm`
- Anchura preferida = `0.3 mm`
- Anchura máxima = `0.5 mm`

- `D` y después `R` > `Design Rules` > `Routing` > `Width_PWR`
- Anchura mínima (PWR) = `0.254 mm`
- Anchura preferida (PWR) = `1 mm`
- Anchura máxima (PWR) = `4 mm`

- `D` y después `R` > `Design Rules` > `Routing` > `Routing Via Style`
- Diámetro de vía = `0.6 mm`
- Diámetro del taladro = `0.3 mm`

#### Máscara
- `D` y después `R` > `Design Rules` > `Mask` > `Solder Mask Expansion`
- Expansión de máscara de soldadura = `0.1 mm`

#### Fabricación
- `D` y después `R` > `Design Rules` > `Manufacturing` > `Hole To Hole Clearance`
- Separación entre taladros = `0.3 mm`

- `D` y después `R` > `Design Rules` > `Manufacturing` > `Minimum Solder Mask Silver`
- Mínimo de máscara de soldadura entre pads = `0.3 mm`

- `D` y después `R` > `Design Rules` > `Manufacturing` > `Silk to Solder Mask Clearance`
- Separación entre serigrafía y máscara = `0.1 mm`

- `D` y después `R` > `Design Rules` > `Manufacturing` > `Silk to Silk Clearance`
- Separación entre elementos de serigrafía = `0.1 mm`

#### Colocación
- `D` y después `R` > `Design Rules` > `Placement` > `Component Clearance`
- Separación vertical entre componentes = `0.2 mm`
- Separación horizontal entre componentes = `0.2 mm`

#### Vías
- `DXP` > `Prefs` > `PCB Editor` > `Defaults` > `Via`
- Diámetro de vía = `0.6 mm`
- Diámetro del taladro = `0.3 mm`

### Stackup
- `Design` > `Layer Stack Manager`
- Cambiar los nombres de las capas a `L1`, `L2`, etc.
- Espesor del dieléctrico o espesor total de la PCB = `1.6 mm`

### Configuración de colores de red
- `View` > `Panels` > `PCB`
- `PCB Panel` > `<Nombre de red>` > `Clic derecho` > `Change Net Color`
- `PCB Panel` > `<Nombre de red>` > `Clic derecho` > `Display Override > Selected ON`
- Color para `GND` = Azul (`236`)
- Color para `PWR` = Naranja (`4`) o Rosa (`1`)
- `F5`: Activar o desactivar los colores de red

---

## Colocación de componentes

- Planificar primero el layout y después la colocación de componentes.
- Comenzar por los componentes **BMC** (*Big, Main and Critical*), como el microcontrolador y los dispositivos de reloj.
- Colocar primero los componentes y conectores con posición predefinida.
- Separar las secciones de alimentación **analógicas** y **digitales**.
- Situar el **driver de reloj** cerca del oscilador.
- Organizar los componentes en filas y columnas cuando sea posible.
- Mantener una **orientación uniforme** en componentes similares, como diodos o condensadores polarizados.
- **Indicar la polaridad** en la serigrafía.
- Colocar todos los componentes en la **cara superior** de la PCB siempre que sea posible.
  - En diseños compactos o complejos, pueden colocarse en la cara inferior únicamente componentes de **baja altura** o de **baja disipación térmica**.
  - No colocar componentes altos en la cara inferior, ya que aumentan la altura total de la PCB.
- Mantener `1 mm (40 mil)` de separación entre componentes y `2.5–3 mm (100–120 mil)` entre componentes y borde de la placa.
- Colocar los **condensadores de desacoplo** lo más cerca posible del circuito integrado.
  - Se recomienda combinar `10 µF` y `100 nF`.
  - El condensador de menor valor debe quedar más próximo al IC.
- Colocar los **conectores** en uno de los bordes de la placa.
- Incluir al menos cuatro **agujeros de montaje**.
- Dejar suficiente espacio alrededor de los agujeros de montaje para la cabeza de los tornillos.
- Dejar más espacio alrededor de **headers** y conectores.
- Colocar los **componentes con mayor disipación térmica** en la cara superior.
- Añadir **puntos de prueba** en todas las redes de alimentación y, cuando sea necesario, en señales críticas y pines de programación.

---

## Enlaces útiles

- [Librerías open source para Altium](https://github.com/amiryeg/Altium-Libraries)
- [Modelos CAD 2D y 3D](https://www.3dcontentcentral.com/)
- [Calculadoras de corriente máxima en pistas de PCB](https://www.eeweb.com/tools/external-pcb-trace-max-current)
- [Calculadoras de ancho de pista](https://www.eeweb.com/tools/external-pcb-trace-width)
- [Calculadora de resistencia de pista en PCB](https://www.eeweb.com/tools/trace-resistance)
- [Calculadoras de impedancia](https://www.eeweb.com/tools/microstrip-impedance)
