# arduino-dj-leds-bpm
# Proyecto: Luces RGB Reactivas a BPM con Arduino y Controladora DJ

## 1. **Introducción**
Este proyecto tiene como objetivo crear un sistema de iluminación RGB que reaccione a los BPM (beats por minuto) de la música, utilizando una controladora DJ y un Arduino. Los LEDs cambiarán de color y ritmo según el canal y la intensidad de la música.

---

## 2. **Materiales Necesarios**
- **Arduino** (Uno, Nano o similar): [Comprar en Amazon](https://www.amazon.es/s?k=arduino)
- **Tira de LEDs RGB** (WS2812B o similar): [Comprar en Amazon](https://www.amazon.es/s?k=ws2812b)
- **Controladora DJ** (con salida de audio o MIDI)
- **Sensor de sonido o entrada de señal de audio**
- **Fuente de alimentación de 5V** (capaz de manejar la corriente de los LEDs)
- **Cables y protoboard**

---

## 3. **Conceptos Fundamentales**

### 3.1. ¿Qué es BPM?
BPM (beats por minuto) mide el tempo de la música. Detectar este valor permite sincronizar las luces con el ritmo.

### 3.2. ¿Por qué WS2812B?
Estos LEDs permiten el control individual de cada pixel y son fáciles de manejar con Arduino mediante bibliotecas especializadas.

---

## 4. **Esquema de Conexión**
- Conectar la tira de LEDs a un pin digital de Arduino (por ejemplo, D6).
- Alimentar los LEDs con una fuente de 5V externa.
- Conectar el sensor de sonido o salida de audio a un pin analógico de Arduino.

**Esquema Básico:**
```
Arduino D6  -->  Data IN WS2812B
5V          -->  VCC WS2812B (fuente externa)
GND         -->  GND WS2812B y Sensor
A0          -->  Salida del sensor de sonido
```

---

## 5. **Software y Librerías**
- **IDE de Arduino**: [Descargar](https://www.arduino.cc/en/software)
- **FastLED Library**: [GitHub - FastLED](https://github.com/FastLED/FastLED)
- **BPM Detector o Análisis FFT**: Opcional según método.

---

## 6. **Desarrollo del Proyecto**

### 6.1. Instalación de Librerías
- Instalar FastLED desde el gestor de bibliotecas del IDE de Arduino.

### 6.2. Detección de BPM
- **Opción 1:** Usar salida de audio con un sensor de sonido.
- **Opción 2:** Utilizar MIDI para obtener BPM directamente desde el software DJ.

### 6.3. Código Base
```cpp
#include <FastLED.h>
#define LED_PIN 6
#define NUM_LEDS 60
CRGB leds[NUM_LEDS];

int sensorPin = A0;
int bpm = 120;

void setup() {
  FastLED.addLeds<WS2812, LED_PIN, GRB>(leds, NUM_LEDS);
  Serial.begin(9600);
}

void loop() {
  int audioValue = analogRead(sensorPin);
  bpm = map(audioValue, 0, 1023, 60, 180);
  colorPattern(bpm);
  FastLED.show();
  delay(1000 / (bpm / 60));
}

void colorPattern(int bpm) {
  for (int i = 0; i < NUM_LEDS; i++) {
    leds[i] = CHSV(random(0, 255), 255, 255);
  }
}
```

---

## 7. **Pruebas y Optimización**
- **Prueba con diferentes canciones** para ajustar la sensibilidad.
- **Optimiza el mapa de BPM** para tener cambios de color más suaves.

---

## 8. **Posibles Mejoras**
- Sincronización con múltiples canales.
- Utilizar diferentes patrones de luz según frecuencias (bajos, medios, agudos).
- Agregar control remoto vía Bluetooth.

---

## 9. **Recursos y Bibliografía**
- [FastLED Documentation](https://fastled.io/)
- [Arduino Forum](https://forum.arduino.cc/)
- [MIDI Protocol](https://www.midi.org/) (si usas MIDI)
- Tutoriales de detección de BPM en YouTube.

---

## 10. **Conclusión**
Este proyecto combina electrónica y música para crear un espectáculo visual adaptado al ritmo de las canciones. Con la flexibilidad de Arduino y FastLED, se pueden personalizar patrones y colores para lograr un efecto impactante en cualquier entorno musical.

