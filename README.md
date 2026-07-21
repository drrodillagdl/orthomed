# OrthoMed — Planeación quirúrgica ortopédica

Herramienta de apoyo para planear osteotomías de rodilla (HTO/DFO),
prótesis total de rodilla, slope tibial y prótesis total de cadera sobre
radiografías digitales. **Un solo archivo, sin instalación, sin internet:**
haz doble clic en `index.html` y se abre en el navegador (Safari o Chrome).

> ⚠️ Herramienta de apoyo a la planeación. No sustituye el juicio clínico ni
> está certificada como dispositivo médico. Verifica siempre la calibración y
> las mediciones.

## Regiones

Arriba a la izquierda hay un selector **Rodilla (frente) / Rodilla
(perfil / slope) / Cadera**. Cada región tiene sus propios puntos,
mediciones y esquema de referencia; la calibración y la imagen se
comparten. El panel muestra una **guía de referencia**: una
**radiografía real** de la región (pelvis AP, pierna AP y rodilla
lateral, incrustadas en el archivo) con los puntos anatómicos marcados
en colores, y debajo una **leyenda color → estructura**. Al tocar
"Colocar" en un punto, su fila de la leyenda **se ilumina** para indicar
cuál es. Los puntos del corte de la osteotomía no aparecen ahí porque
dependen de tu planeación, no de un punto anatómico fijo.

> Las radiografías de la guía las aportó el Dr. Si vas a distribuir la
> herramienta, asegúrate de tener los derechos de esas imágenes y de que
> no lleven datos identificables de pacientes.

## Flujo de trabajo (rodilla)

1. **Cargar radiografía** — telemetría de pierna completa AP (ideal) en
   JPG/PNG. También puedes arrastrarla a la ventana o pegarla con ⌘V
   (por ejemplo, una captura del visor PACS).
2. **Calibrar** — clic en los dos extremos del marcador del estudio
   (esfera de 25 mm o regla) y escribe su tamaño real. Sin calibrar, los
   ángulos son válidos pero los milímetros no.
3. **Puntos anatómicos** — la app te va guiando:
   - Cabeza femoral: 3 puntos sobre su contorno (calcula el centro).
   - Centro de rodilla: espinas tibiales.
   - Línea articular femoral: cóndilo **medial primero**, luego lateral.
   - Meseta tibial: borde **medial primero**, luego lateral.
   - Tobillo: bordes del plafond, **medial primero**.
   - Todos los puntos se pueden arrastrar después para afinarlos.
4. **Mediciones automáticas** — HKA, MAD, WBL (%), mLDFA, MPTA y JLCA,
   con rangos normales resaltados en verde/naranja.
5. **Osteotomía (método de Miniaci)** — elige el tipo: **HTO** (tibial
   alta) o **DFO** (femoral distal). Coloca la **bisagra** y la
   **entrada** del corte sobre el hueso correspondiente y elige el punto
   objetivo (62% Fujisawa en HTO; 50% neutro en DFO). La app calcula el
   ángulo de corrección, la **cuña en mm** (y si es de **apertura o
   cierre**, según dónde pusiste bisagra y entrada), los ángulos
   post-corrección (MPTA post en HTO, mLDFA post en DFO — un MPTA post
   >95° sugiere doble osteotomía) y puede **simular la corrección**
   rotando el fragmento distal. En la DFO el cálculo rota también la
   rodilla y la meseta con el fragmento, como corresponde.
6. **Prótesis total (PTR)** — marca el **eje anatómico femoral** (2
   puntos en la diáfisis) y activa "Mostrar cortes". La app dibuja las
   líneas de resección femoral distal y tibial proximal (perpendiculares
   a los ejes mecánicos) con los **mm de resección medial y lateral** en
   la imagen, y calcula el **ángulo valgo** entre eje mecánico y
   anatómico (el que se fija en la guía intramedular). La resección
   femoral se referencia del cóndilo más distal. Para la tibia puedes
   elegir la **referencia**: *platillo sano* (el más alto, resecando
   ~8–10 mm, técnica clásica) o *platillo desgastado* (el más bajo,
   resecando ~2 mm). Todas las profundidades son configurables.
7. **Exportar PNG** — genera una lámina con la imagen planificada y el
   resumen de mediciones para el expediente. **Guardar plan** crea un
   archivo `.json` que puedes reabrir después para seguir editando.

## Flujo de trabajo (cadera — prótesis total)

Cambia la región a **Cadera** y usa una radiografía **AP de pelvis** con
marcador de calibración. Coloca:

1. **Gotas de lágrima** (teardrop) derecha e izquierda → línea
   interlagrimal, la referencia horizontal de la pelvis.
2. **Cabeza femoral (a operar)** (3 puntos) → centro de rotación y
   diámetro de la cabeza.
3. **Trocánter menor** (a operar y contralateral) → **discrepancia de
   longitud** (compara la distancia de cada uno a la línea interlagrimal
   e indica si la pierna a operar queda más corta o más larga).
4. **Trocánter mayor** (punta, lado a operar) → orienta la línea del
   **corte de cuello** (de la cortical medial hacia el troc. mayor).
5. **Eje femoral (a operar)** (2 puntos en el canal) → **offset femoral**
   (distancia del centro de la cabeza al eje).
6. **Cabeza femoral contralateral** (3 puntos sobre la cadera SANA) → su
   centro de rotación se **refleja sobre la línea media pélvica** para
   marcar el **COR objetivo** (cruz verde) del lado a operar. La tabla
   dice cuánto **medializar/lateralizar** y **subir/bajar** el centro
   para igualar la cadera sana, y compara los diámetros de cabeza.
7. **Eje femoral contralateral** (2 puntos en el canal sano) →
   **offset objetivo**. La tabla compara el offset del lado a operar con
   el sano y dice cuánto **aumentar o reducir** el offset del vástago
   para igualar la cadera sana. Junto con la discrepancia de longitud,
   define la reconstrucción: cuánto alargar y cuánto lateralizar.
8. **Ancho acetabular** (reborde superolateral → fondo inferomedial) →
   **referencia de copa en mm** (≈ diámetro a reamar; las copas vienen
   en pasos de 2 mm).
9. **Ancho del canal femoral** (endostio medial → lateral, a la altura
   donde asentará el vástago) → **referencia de vástago en mm**.

En **Prótesis total (PTC)** defines el plan: **cadera a operar
(derecha/izquierda)** — con esto el reborde de la copa se orienta
correctamente (borde lateral superior); **inclinación** y **diámetro de
copa** a probar (se dibuja el cotilo sobre el centro de rotación); y el
**nivel de resección del cuello**, medido en mm sobre el **trocánter
menor**: la línea del corte va de la cortical medial (calcar) hacia el
**trocánter mayor**, como la osteotomía real del cuello.
Exportar PNG genera el reporte con todos estos datos.

> Todo esto son medidas y referencias 2D sobre la radiografía: dependen
> de una rotación neutra de la cadera (rótulas al frente) y de buena
> calibración. Las referencias de copa y canal son el **tamaño medido**
> del hueso, no un templado de un implante específico ni sustituyen las
> plantillas del fabricante; úsalas como punto de partida.

## Flujo de trabajo (rodilla de perfil — slope tibial)

Cambia la región a **Rodilla (perfil / slope)** y usa una radiografía
**lateral de rodilla** (idealmente cóndilos superpuestos). Coloca:

1. **Eje tibial proximal** (2 puntos al centro de la diáfisis).
2. **Meseta (perfil)**: borde **anterior** y luego **posterior**.
   → la app calcula la **pendiente tibial posterior (PTS)**. Normal
   ~7–10°; se resalta en naranja si supera 12° (factor de riesgo de
   re-ruptura del injerto del LCA).
3. **Osteotomía de slope** (opcional): marca la **bisagra** (cortical
   posterior, respetar ~10 mm) y el **ápice anterior** del corte, y fija
   el **slope objetivo** (5° por defecto). La app calcula el ángulo de
   corrección, la **cuña anterior a resecar en mm** (osteotomía de cierre
   anterior / sustracción), dibuja la cuña y la meseta ya corregida
   (verde), y puede **simular la corrección** rotando el fragmento
   proximal para dejar el slope en el objetivo.

> Es una osteotomía de sustracción anterior supratuberositaria: reduce el
> slope posterior para descargar el injerto del LCA en pacientes con
> slope alto y re-rupturas. La app supone una lateral verdadera; con
> cóndilos no superpuestos la PTS varía varios grados.

## Consejos de precisión

- Usa telemetría con apoyo (carga) y marcador de calibración a la altura
  de la rodilla; la magnificación cambia con la distancia al detector.
- La rótula debe apuntar al frente (rotación altera mLDFA/MPTA).
- Si el JLCA es > 3–4°, parte de la deformidad es intraarticular:
  considera restarlo del objetivo de corrección.

## Pendientes / siguientes versiones

- Plantillas de tamaños de componentes protésicos superponibles.
- Lectura directa de DICOM (.dcm) con escala automática.
- Doble osteotomía (HTO + DFO combinadas en un mismo plan).
- Exportar el reporte a PDF además de PNG.
