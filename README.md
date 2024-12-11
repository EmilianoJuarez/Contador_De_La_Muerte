# README: Contador BCD Simulado en Proteus

Este documento describe el funcionamiento, componentes y configuración de un contador BCD diseñado en el simulador Proteus. Este proyecto está orientado a ilustrar cómo implementar un contador binario codificado en decimal (BCD) utilizando circuitos integrados lógicos de la familia 74LS y otros componentes electrónicos.

## Descripción del Proyecto

El contador BCD diseñado puede contar de 00 a 99, representando los valores en dos displays de 7 segmentos. Incluye la capacidad de incrementar y restablecer el conteo mediante señales externas. Este circuito es útil como base para aplicaciones como cronómetros, temporizadores o cualquier sistema que requiera contadores decimales.

### Componentes Principales

1. **Contadores BCD (74LS192):**
   - Se utilizan dos circuitos 74LS192 para manejar cada uno de los dígitos (decenas y unidades).
   - Cada contador tiene entradas de conteo ascendente (UP) y descendente (DOWN), así como una entrada de reinicio (MR).

2. **Decodificadores BCD a 7 segmentos (74LS48):**
   - Los decodificadores 74LS48 se encargan de convertir la salida BCD de los contadores en señales que controlan los displays de 7 segmentos.

3. **Comparador lógico (74LS85):**
   - Se utiliza para comparar el valor de los contadores y establecer condiciones específicas en el circuito, como alcanzar un valor límite.

4. **Puerta lógica (AND - 74LS08):**
   - Permite combinar señales lógicas para controlar el comportamiento del circuito.

5. **Displays de 7 segmentos:**
   - Representan los dígitos del contador de manera visual.

6. **Componentes auxiliares:**
   - Resistencias, LEDs, transistores (2N2222A) y fuentes de alimentación para completar la implementación del circuito.

## Funcionamiento del Circuito

1. **Incremento del conteo:**
   - Al recibir una señal en la entrada UP del primer contador (74LS192), el dígito de las unidades incrementa.
   - Cuando el dígito de unidades alcanza 9 y recibe un nuevo pulso, genera un acarreo hacia el contador de decenas.

2. **Visualización en los displays:**
   - Las salidas del 74LS192 (QA, QB, QC, QD) se conectan a las entradas del 74LS48, que se encarga de controlar los segmentos de cada display.

3. **Reinicio del contador:**
   - Una señal en la entrada MR de los contadores restablece el valor a 00.

4. **Condiciones de comparación:**
   - El 74LS85 puede configurarse para detener el conteo o activar salidas específicas al alcanzar un valor límite predefinido.

5. **Control de los displays:**
   - Los decodificadores 74LS48 manejan directamente los displays de 7 segmentos, activando los segmentos necesarios para formar cada dígito.

## Esquema del Circuito

El esquema fue diseñado y simulado en Proteus. Incluye:
   - Dos etapas de conteo (unidades y decenas).
   - Entradas para señales de conteo ascendente (UP), reinicio (MR), y configuraciones específicas mediante el comparador.
   - Salidas visuales a través de displays de 7 segmentos.

## Posibles Extensiones del Proyecto

1. **Adición de conteo descendente:**
   - Utilizando las entradas DOWN de los contadores.

2. **Programación de un límite dinámico:**
   - Con switches DIP para configurar el valor máximo.

3. **Integración con microcontroladores:**
   - Sustituyendo algunas etapas del circuito con un microcontrolador para mayor flexibilidad.

4. **Implementación física:**
   - Llevar el diseño del simulador a un protoboard o PCB.

## Requerimientos para la Simulación

- **Software:** Proteus 8 o superior.
- **Biblioteca:** Incluye los componentes de la familia 74LS.
- **Configuración:** Conectar correctamente las entradas y salidas, según el esquema mostrado en la simulación.

## Cómo Correr la Simulación

1. Abre el archivo del proyecto en Proteus.
2. Asegúrate de que todos los componentes están correctamente conectados.
3. Ejecuta la simulación y observa el comportamiento del contador en los displays.
4. Modifica las señales de entrada (UP y MR) para ver el efecto en tiempo real.

---

Para más detalles o para descargar el archivo del simulador, visita este repositorio.

