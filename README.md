# ReproTP21d
Calculadora de tasas reproductivas

https://josefernandoguarin.github.io/ReproTP21d
https://josefernandoguarin.github.io/ReproTP21d/Reproduccion_Lechera_FCA_Instrucciones.pdf

Reproducción Lechera FCA
Facultad de Ciencias Agrarias · Universidad de Antioquia

Aplicación web que calcula las tasas reproductivas de un hato lechero a partir de los registros de la hacienda: tasa de servicio (TS), tasa de concepción (TC) y tasa de preñez a 21 días (TP21), en ciclos de 21 días después del período de espera voluntario (PEV). Es un solo archivo HTML y los datos no salen del navegador.

Cómo abrirla
Local: abra reproduccion-lechera.html en Chrome, Edge o Firefox. Para leer archivos de Excel necesita internet la primera vez, porque el lector de hojas de cálculo se carga de la red. Sin conexión, copie la tabla en Excel y péguela en la app.
En línea: use el enlace publicado. Es privado; para compartirlo, use el menú Compartir de la página.
La app abre con una hacienda simulada de 96 vacas para practicar.

Flujo de trabajo
Registros. Cargue el libro de la hacienda (.xlsx, .xls o .csv) o pegue una tabla. Si el libro trae varias tomas mensuales con fecha en el nombre de la hoja (por ejemplo «31-08-25»), la app las marca todas y las combina por vaca y fecha de parto.
Parámetros. Declare el PEV (días), la duración del ciclo (21 d), los días necesarios para diagnosticar preñez, la fecha de corte, el rango de análisis, el lote y las metas.
Columnas y estados. Revise las columnas que la app propuso: identificación, FUP, FPS, FUS, servicios 1, 2, 3…, número de servicios, estado, FPP y lote. Después indique qué significa cada valor de estado (p+, PR, s, Ser, vacia, Palp-, Nc…).
Calcular tasas. Vea los resultados en Tasas reproductivas y el detalle de cada animal en Vacas.
Formatos de registro que acepta
Formato	Ejemplo	Qué necesita
Una fila por vaca	Estado de ganadería mensual, hoja RESUMEN del balance de ración	Identificación, FUP y fechas de servicio (FPS, FUS o servicios 1…n). El estado sirve para saber si quedó preñada.
Una fila por evento	Hoja de servicios de la plantilla de reproducción	Identificación, fecha y tipo de evento (parto, servicio, palpación positiva o negativa, salida).
Definiciones
Disponible para IA: vaca que ya pasó el PEV (FUP + PEV), no está preñada al iniciar el ciclo y sigue en el hato.
TS % = inseminadas / disponibles × 100
TC % = preñadas / inseminadas × 100
TP21 % = preñadas / disponibles × 100 (≈ TS × TC)
Hay dos formas de armar los ciclos:

Ciclos de cada vaca (por defecto): el ciclo 1 va del día PEV al día PEV + 20 del posparto, el ciclo 2 de PEV + 21 a PEV + 41, y así sucesivamente.
Períodos de calendario: bloques de 21 días desde la fecha «Analizar desde», para seguir la evolución del hato en el tiempo.
Los ciclos que terminan a menos de «días para diagnosticar» de la fecha de corte quedan pendientes y no entran en las tasas. Si una vaca figura como servida y su último servicio ya debería estar diagnosticado, ese ciclo se marca sin diagnóstico y se excluye de TC y TP21.

Qué muestra
Las tres tasas con un semáforo frente a la meta.
Una gráfica por ciclo: barras de TP21 y TS, y línea de TC.
Una tabla por ciclo con disponibles, inseminadas, preñadas, sin diagnóstico y pendientes. Se puede copiar a Excel.
Otros indicadores: % del hato preñado, días a primer servicio, días abiertos, servicios por concepción, vacías con más de 150 DEL, vacas sin servicio después del PEV + 21 d y servicios antes del PEV.
Por vaca: FUP, DEL, estado, fechas de servicio, concepción, días abiertos, una fila de ciclos (· disponible no servida, I inseminada, P preñada, ? pendiente) y avisos.
Calidad de los datos
Para calcular las tasas se necesitan las fechas de cada servicio. Si un archivo solo trae FPS y FUS, los servicios intermedios no se pueden ubicar en un ciclo: la TS queda subestimada y la TC sobrestimada. La app avisa cuántas vacas tienen más servicios declarados que fechas. Para reducir el problema:

combine varias tomas mensuales, o
acote el análisis a fechas cubiertas por las tomas, o
use un registro de eventos con cada servicio.
Si no hay ninguna fecha de servicio, como en la hoja RESUMEN de 2022, la app lo indica y no calcula tasas.

Datos guardados
La última carga y los parámetros se guardan en el navegador del usuario. Cargar datos de ejemplo vuelve a la hacienda simulada.
