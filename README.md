# Características del sensor seleccionado: HC-SR501 Body Sensor Module

## 1. Sensor seleccionado

El sensor seleccionado para el desarrollo de la actividad es el **HC-SR501 Body Sensor Module**, un módulo basado en tecnología **PIR (Passive Infrared Sensor)**, utilizado para detectar movimiento o presencia de personas a partir de la radiación infrarroja emitida por el cuerpo humano. :contentReference[oaicite:0]{index=0}

En el contexto del proyecto propuesto, este sensor se utilizaría para **detectar si una persona está cerca de un expendedor de medicamentos**, de manera que el sistema pueda interactuar con un **RTC** y permitir el desbloqueo únicamente en el horario correspondiente a la toma del medicamento. Esta descripción corresponde únicamente al uso planteado en la actividad; las características técnicas listadas a continuación fueron tomadas solo de los documentos proporcionados. 

---

## 2. Hoja(s) de datos utilizadas

Para identificar las características del sensor se utilizaron únicamente los siguientes documentos proporcionados:

- **HC-SR501.pdf** :contentReference[oaicite:2]{index=2}
- **31227sc.pdf** :contentReference[oaicite:3]{index=3}
- **Sensores_y_actuadores.pdf** (material de clase) :contentReference[oaicite:4]{index=4}

---

## 3. Tabla de características del sensor (mapa a conceptos vistos en clase)

| Característica (concepto de clase) | Valor / información encontrada en los PDFs | Fuente |
|---|---|---|
| **Tipo de sensor / transductor** | PIR — sensor piroeléctrico (pasivo). | :contentReference[oaicite:5]{index=5} |
| **Rango operativo (tensión)** | DC **4.5 – 20 V** (rango operativo indicado). | :contentReference[oaicite:6]{index=6} |
| **Consumo / corriente en reposo** | Reportes diferentes: **“Quiescent Current <50 µA”** en una especificación; otro documento indica **Power Consumption: 65 mA**. Ambos están en los PDFs. Discrepancia documentada abajo. |  |
| **Nivel de salida** | TTL: **High = 3.3 V / Low = 0 V** (salida compatible con lógica). | :contentReference[oaicite:8]{index=8} |
| **Modo de disparo (trigger)** | Dos modos seleccionables por jumper: **L = no-repeat trigger** (dispara una vez y espera), **H = repeatable trigger** (mantiene HIGH si hay movimiento dentro del periodo de retardo). |  |
| **Tiempo de retardo (delay)** | Potenciómetro ajustable. Valores reportados: **5–200 s** (HC-SR501.pdf) y **0.3–5 min / 5–300 s** (aprox.) en otra fuente. Indican que girar el potenciómetro en sentido horario aumenta el delay. |  |
| **Tiempo de bloqueo (block time / dead time)** | **Default 2.5 s** (se puede ajustar a un rango de fracciones de segundo hasta decenas de segundos). | :contentReference[oaicite:11]{index=11} |
| **Ángulo de detección (apertura)** | Documentos indican **<100°** en uno y **<110°** en otro. Se reportan ambos valores. |  |
| **Alcance (distancia de detección)** | Hasta **≈7 m** (ajustable mediante potenciómetro; mínimo señalado ≈3 m). |  |
| **Tamaño de lente** | Diámetro de lente: **23 mm** (aprox.). | :contentReference[oaicite:14]{index=14} |
| **Dimensiones del módulo** | **32 mm × 24 mm** (distancia entre tornillos ~28 mm, M2). | :contentReference[oaicite:15]{index=15} |
| **Temperatura de operación** | **−15 °C a +70 °C**. | :contentReference[oaicite:16]{index=16} |
| **Inicialización** | Al encender necesita **~1 minuto de inicialización**; durante ese tiempo puede sacar **0–3 pulsos/min** antes de estabilizar. |  |
| **Control fotosensible (opcional)** | Opción para activar control por luminosidad, para evitar detección en días muy luminosos. Es opcional y no siempre viene configurado de fábrica. | :contentReference[oaicite:18]{index=18} |
| **Compensación de temperatura (opcional)** | Se menciona posibilidad de compensación térmica para reducir la disminución del alcance en ambientes calurosos. Es opcional y no siempre está activado. | :contentReference[oaicite:19]{index=19} |
| **Dual-probe / orientación de montaje** | El módulo tiene doble sub-probe y es más sensible al movimiento lateral (izquierda a derecha o derecha a izquierda) que al movimiento frontal (hacia o desde el sensor). Se recomienda orientar la placa paralela al patrón de movimiento humano. |  |
| **Aplicaciones típicas** | Seguridad, iluminación automática, juguetes, control industrial, puertas automáticas, entre otras. | :contentReference[oaicite:21]{index=21} |
| **Función de transferencia** | No viene definida numéricamente en las hojas proporcionadas. No hay curva Vout vs estímulo térmico ni ganancia ni sensibilidad en unidades físicas. No hay datos experimentales en los PDFs. |  |
| **Sensibilidad (valor numérico)** | No proporcionado en los PDFs. No aparece una sensibilidad en V/°C, µV, o similar. El documento describe cómo la orientación afecta la sensibilidad, pero no da coeficiente numérico. | :contentReference[oaicite:23]{index=23} |
| **Exactitud / incertidumbre / precisión / resolución / histéresis / saturación** | No hay valores cuantitativos en las hojas suministradas. Las notas de clase definen estos conceptos, pero la hoja del sensor no trae cifras de exactitud ni resolución en esos términos. |  |

---

## 4. Explicación de las características identificadas

### 4.1 Tipo de sensor

El HC-SR501 es un **sensor PIR**, es decir, un sensor infrarrojo pasivo. Este tipo de sensor detecta variaciones en la radiación infrarroja del entorno, especialmente la emitida por el cuerpo humano. :contentReference[oaicite:25]{index=25}

### 4.2 Variable detectada

La variable detectada está asociada a la **radiación infrarroja** proveniente de los cuerpos. Gracias a ello, el sensor puede identificar presencia o movimiento dentro de su zona de detección. :contentReference[oaicite:26]{index=26}

### 4.3 Alimentación

El módulo trabaja con una tensión de alimentación entre **4.5 V y 20 V DC**. :contentReference[oaicite:27]{index=27}

### 4.4 Salida digital

La salida del sensor es digital, con niveles TTL:

- **HIGH = 3.3 V**
- **LOW = 0 V** :contentReference[oaicite:28]{index=28}

### 4.5 Distancia y ángulo de detección

La distancia de detección es ajustable y puede llegar aproximadamente hasta **7 metros**, mientras que el ángulo de detección reportado en los documentos está entre **<100° y <110°**. 

### 4.6 Retardo y modos de trabajo

El sensor incorpora un potenciómetro que permite ajustar el tiempo de retardo, y un jumper para seleccionar entre modo repetible y no repetible. Esto permite adaptar el comportamiento del sensor según la aplicación. 

### 4.7 Inicialización y bloqueo

Al encenderse, el sensor requiere un tiempo de estabilización cercano a **1 minuto**. También presenta un tiempo de bloqueo predeterminado de **2.5 segundos**. 

---

## 5. Conceptos vistos en clase

Esta sección conecta la hoja de datos del HC-SR501 con los conceptos teóricos trabajados en la clase. :contentReference[oaicite:32]{index=32}

### 5.1 Sensor como transductor pasivo

De acuerdo con el material de clase, un sensor puede entenderse como un **transductor**, ya que convierte una magnitud física en una señal eléctrica medible. En este caso, el HC-SR501 actúa como un **transductor pasivo**, porque detecta la **radiación infrarroja** emitida por el cuerpo humano y la transforma en una señal eléctrica de salida que luego puede ser interpretada por un sistema electrónico. 

Esto significa que el sensor no mide contacto físico ni distancia directa, sino que responde a cambios en la energía infrarroja del entorno, principalmente asociados a la presencia de personas. Desde el punto de vista de la teoría vista en clase, esta es la relación más clara entre el dispositivo seleccionado y el concepto de sensor/transductor. 

### 5.2 Sensibilidad, resolución, exactitud y otros parámetros de metrología

En las notas de clase aparecen conceptos como **sensibilidad**, **resolución**, **exactitud**, **precisión**, **incertidumbre**, **histéresis**, **saturación** y **función de transferencia**. :contentReference[oaicite:35]{index=35}

Sin embargo, al revisar las hojas de datos suministradas del HC-SR501, **no se encontraron valores numéricos explícitos** para esas características metrológicas. Es decir:

- no aparece una sensibilidad expresada en unidades físicas como V/°C, µV o similares,
- no se especifica resolución,
- no se reportan valores de exactitud o precisión,
- no se muestran curvas completas de función de transferencia,
- no se indican valores cuantitativos de histéresis o saturación. 

Por esa razón, **no es correcto asumir ni inventar esos valores**. Lo único que sí puede describirse a partir de la información entregada son ciertos **comportamientos del sensor** que se relacionan indirectamente con esos conceptos, por ejemplo:

- la sensibilidad cambia según la **orientación del movimiento** de la persona frente al sensor,
- el comportamiento puede modificarse mediante los **potenciómetros de ajuste**,
- el rendimiento puede verse afectado por la **temperatura del entorno**,
- existe posibilidad de **compensación térmica** y de **control fotosensible**. 

En consecuencia, desde la perspectiva de la actividad, sí es posible relacionar el HC-SR501 con los conceptos vistos en clase, pero debe aclararse que **la hoja de datos no proporciona todas las magnitudes numéricas teóricas** que normalmente se buscan en el análisis de sensores. 

---

## 6. Discrepancias encontradas entre las fuentes

Durante la revisión de los documentos suministrados se encontraron algunas diferencias en ciertos parámetros del sensor:

- **Tiempo de retardo:** un documento reporta **5–200 s**, mientras que otro indica **5–300 s** o aproximadamente **0.3–5 min**. 
- **Ángulo de detección:** una fuente indica **<100°** y otra **<110°**. 
- **Consumo:** una hoja muestra **quiescent current <50 µA**, mientras otra reporta **power consumption 65 mA**. 

Estas diferencias se dejan registradas tal como aparecen en los documentos, sin suponer cuál de los valores es el definitivo.

---

## 7. Aplicación del sensor en el proyecto propuesto

En el proyecto planteado, el HC-SR501 puede emplearse para detectar si una persona se encuentra cerca del expendedor de medicamentos. Una vez detectada la presencia, el sistema podría consultar un **RTC** para determinar si el horario corresponde al momento programado para la toma del medicamento y, en caso afirmativo, permitir el desbloqueo del dispositivo.

De esta manera, el sensor funcionaría como el elemento encargado de detectar presencia humana, mientras que el RTC controlaría la lógica temporal del acceso. Esta explicación corresponde únicamente al uso propuesto en la actividad. 

---

## 8. Conclusión

El **HC-SR501 Body Sensor Module** es un sensor PIR útil para aplicaciones de detección de presencia o movimiento humano. A partir de las hojas de datos suministradas fue posible identificar varias características relevantes, como tensión de operación, nivel de salida, distancia y ángulo de detección, modos de disparo, tiempo de retardo, temperatura de operación e inicialización.

Además, al relacionarlo con los conceptos vistos en clase, se puede afirmar que funciona como un **transductor pasivo**, ya que convierte radiación infrarroja en señal eléctrica. También se concluye que varias propiedades teóricas importantes, como sensibilidad numérica, exactitud, resolución y función de transferencia, **no están reportadas cuantitativamente** en las hojas entregadas, por lo que no deben asumirse valores no documentados. 

---

## 9. Referencias

- **HC-SR501.pdf** :contentReference[oaicite:44]{index=44}
- **31227sc.pdf** :contentReference[oaicite:45]{index=45}
- **Sensores_y_actuadores.pdf** :contentReference[oaicite:46]{index=46}
