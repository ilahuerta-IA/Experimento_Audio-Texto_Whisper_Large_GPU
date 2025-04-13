# Experimento con Whisper 'large' en GPU (Google Colab)

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ilahuerta-IA/Experimento_Audio-Texto_Whisper_Large_GPU/blob/main/Experimento_Whisper_Large_GPU.ipynb)
_**(¡Haz clic en la insignia de arriba para abrir y ejecutar el cuaderno directamente en Google Colab!)**_

## Objetivo

Este repositorio contiene un cuaderno de Google Colab (`.ipynb`) diseñado para replicar fácilmente un experimento básico con el modelo **Whisper `large` de OpenAI**, aprovechando las **GPUs gratuitas** proporcionadas por Colab.

El objetivo es permitir a cualquier desarrollador:

1.  **Ejecutar** el modelo Whisper `large` en un entorno GPU accesible.
2.  **Medir** el rendimiento básico (tiempo de carga del modelo, tiempo de transcripción).
3.  **Observar** el uso de recursos (VRAM de la GPU, RAM del sistema).
4.  **Evaluar** la calidad de la transcripción resultante para sus propios archivos de audio.

Este experimento se basa en la "Fase 0" del proyecto original [Audio-WhatsApp-a-texto](https://github.com/ilahuerta-IA/Audio-WhatsApp-a-texto), centrándose específicamente en la ejecución en GPU.

## Resultados Clave (Ejemplo en Tesla T4)

Durante las pruebas iniciales (los resultados pueden variar según la GPU asignada y el archivo de audio):

*   **Tiempo de Carga (Modelo `large`):** ~68 segundos.
*   **Tiempo de Transcripción (Audio de prueba de 5 minutos, FP32):** ~66 segundos.
*   **Uso Pico de VRAM:** ~9.6 GB (¡Requiere una GPU con suficiente memoria!).
*   **Calidad:** Notablemente superior a modelos más pequeños o ejecuciones en CPU.

**¡Te animo a ejecutar el cuaderno con tus propios audios para ver tus resultados!**

Aquí una captura de ejemplo de la ejecución en Colab mostrando los resultados y el uso de recursos:

![Captura de pantalla de ejecución en Colab](assets/Captura%20de%20pantalla%20Whisper%20Large%20GPU.png) 

## Cómo Usar el Cuaderno en Google Colab

1.  **Abrir en Colab:** Haz clic en la insignia [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ilahuerta-IA/Experimento_Audio-Texto_Whisper_Large_GPU/blob/main/Experimento_Whisper_Large_GPU.ipynb) al principio de este README.
2.  **Seleccionar Entorno GPU:** Una vez abierto en Colab, ve al menú `Entorno de ejecución` -> `Cambiar tipo de entorno de ejecución`. Asegúrate de que `Acelerador por hardware` esté configurado como `GPU`. Guarda los cambios.
3.  **Subir tu Archivo de Audio:** Usa el panel de archivos de la izquierda en Colab (icono de carpeta) para subir el archivo de audio (`.mp3`, `.wav`, `.m4a`, etc.) que quieres probar.
4.  **¡IMPORTANTE! Modificar Ruta del Archivo:**
    *   En el panel de archivos, busca tu archivo subido.
    *   Haz clic derecho sobre él y selecciona `Copiar ruta`.
    *   Ve a la **Celda 1** del cuaderno (`# Celda 1: Importaciones y Configuración Inicial`). Busca la línea que define `RUTA_AUDIO_ORIGINAL_STR`.
    *   **Pega la ruta que copiaste** para reemplazar el valor existente (ej: `RUTA_AUDIO_ORIGINAL_STR = "/content/mi_audio_subido.wav"`).
5.  **Ejecutar las Celdas:** Ejecuta todas las celdas del cuaderno en orden. Puedes usar `Entorno de ejecución` -> `Ejecutar todas` o ejecutar cada celda individualmente (Shift + Enter).
6.  **Observar Resultados:**
    *   Presta atención a la **salida impresa** debajo de cada celda (tiempos, texto transcrito).
    *   **Monitoriza los indicadores `RAM` y `GPU RAM`** en la esquina superior derecha de Colab, especialmente durante la ejecución de las celdas que cargan el modelo y realizan la transcripción, para ver el uso de recursos.

## Contenido del Repositorio

*   `Experimento_Whisper_Large_GPU.ipynb`: El cuaderno de Google Colab con el código y las explicaciones paso a paso. **Nota:** El cuaderno clona el repositorio _original_ ([Audio-WhatsApp-a-texto](https://github.com/ilahuerta-IA/Audio-WhatsApp-a-texto)) dentro de Colab para acceder a los módulos Python necesarios.
*   `README.md`: Este archivo de explicación.
*   `src/`: Contiene copias de los módulos Python (`audio_handler.py`, `config.py`) del proyecto original, incluidas aquí para referencia o si se desea adaptar el experimento para no depender del clonado del otro repositorio.
*   `LICENSE`: (Si se incluye) Archivo de licencia.
*   `.gitignore`: (Si se incluye) Archivo para ignorar elementos en Git.

## Dependencias (Instaladas por el Cuaderno)

El propio cuaderno se encarga de instalar las dependencias necesarias dentro del entorno de Colab:

*   `ffmpeg`
*   `openai-whisper`
*   `pydub`


## Licencia

Este proyecto se distribuye bajo la licencia MIT. Consulta el archivo `LICENSE` si se incluye.

---

