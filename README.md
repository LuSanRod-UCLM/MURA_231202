| Supported Targets | ESP32 | ESP32-C2 | ESP32-C3 | ESP32-C6 | ESP32-H2 | ESP32-S2 | ESP32-S3 |
| ----------------- | ----- | -------- | -------- | -------- | -------- | -------- | -------- |

# _Buffers circulares_

Ejemplo de intercambio de información mediante buffers circulares con acceso en exclusión mutua

La aplicación muestra el empleo de dos buffers circulares muy simples para compartir información entre tres tareas.
La primera lee un valor analógico, la segunda calcula la media de una serie de valores y la tercera muestra las medias almacenadas.


## Como usar el ejemplo
Este ejemplo está pensado para ser utilizado en Visual Studio Code con la extensión Espressif IDF.
Compile, monte y carge el ejemplo en la placa de desarrollo.
Conectando un potenciometro al canal 0 del ADC1 (GPIO36) se puede seguir la evolución de las medias de los valores registrados en un monitor ESP-IDF.

## Contenido del directorio de ejemplo

Los archivos que forman el ejemplo contienen código C y están en la carpeta [main](main).

Los proyecctos ESP-IDF se construyen usando CMake. La configuración de construcción del proyecto está en `CMakeLists.txt`

Debajo hay una breve explicación del contenido principal del directorio del proyecto.

```
├── CMakeLists.txt             CMake principal
├── main
│   ├── CMakeLists.txt 
│   ├── analogInput.h          Interfaz de la tarea de lecturas analógicas
│   ├── analogInput.c          Realización de la tarea de lecturas analógicas
│   ├── calculaMedias.h        Interfaz de la tarea de cálculo de valores medios
│   ├── calculaMedias.c        Realización de la tarea de cálculo de valores medios
│   ├── calculaMedias.h        Interfaz de la tarea de cálculo de valores medios
│   ├── calculaMedias.c        Realización de la tarea de cálculo de valores medios
│   ├── informe.h              Interfaz de la tarea de informe de valores medios
│   ├── informe.c              Realización de la tarea de informe de valores medios
│   ├── bufferCircular.h       Interfaz de la librería de gestión de buffers circulares
│   ├── bufferCircular.c       Realización de la librería de gestión de buffers circulares
│   ├── myTask.h               Interfaz de la librería para facilitar la plafinicación de tareas
│   ├── myTask.c               Realización de la librería para facilitar la plafinicación de tareas
│   └── mura_231202_main.c     Archivo con el programa principal del proyecto
└── README.md                  Este archivo que estás leyendo
```
