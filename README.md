# Yolov5
# Aplicación de Detección de Objetos en Tiempo Real

Esta aplicación web permite realizar detección de objetos en tiempo real utilizando la cámara web del dispositivo. Está construida con Streamlit y utiliza el modelo YOLOv5 para la detección de objetos.

## Características

- Captura de imágenes en tiempo real mediante la cámara web
- Detección de múltiples objetos en una sola imagen
- Interfaz gráfica interactiva con controles ajustables
- Visualización de resultados con bounding boxes
- Conteo y clasificación de objetos detectados

## Requisitos

```
cv2
yolov5
streamlit
numpy
pandas
```

## Instalación

1. Clone este repositorio:
```bash
git clone <url-del-repositorio>
cd <nombre-del-directorio>
```

2. Instale las dependencias:
```bash
pip install -r requirements.txt
```

3. Descargue el modelo pre-entrenado YOLOv5:
```bash
wget https://github.com/ultralytics/yolov5/releases/download/v6.1/yolov5s.pt
```

## Uso

1. Ejecute la aplicación:
```bash
streamlit run app.py
```

2. Acceda a la aplicación a través de su navegador web (por defecto en `http://localhost:8501`)

3. Configure los parámetros de detección en la barra lateral:
   - **IoU (Intersection over Union)**: Ajuste el umbral de superposición para la detección de objetos (0-1)
   - **Confidence**: Ajuste el umbral de confianza para las detecciones (0-1)

4. Utilice el botón "Capturar foto" para tomar una imagen con su cámara web

## Estructura de la Aplicación

La aplicación se divide en dos secciones principales:

### Barra Lateral (Sidebar)
- Controles deslizantes para ajustar los parámetros IoU y Confidence
- Visualización en tiempo real de los valores seleccionados

### Área Principal
- Interfaz de captura de imagen
- Visualización de resultados en dos columnas:
  - Columna 1: Imagen con las detecciones marcadas
  - Columna 2: Tabla de resumen con el conteo de objetos detectados

## Parámetros del Modelo

- `model.conf = 0.25` - Umbral de confianza para NMS (Non-Maximum Suppression)
- `model.iou = 0.45` - Umbral IoU para NMS
- `model.agnostic = False` - NMS específico por clase
- `model.multi_label = False` - Una etiqueta por caja
- `model.max_det = 1000` - Número máximo de detecciones por imagen

## Funcionamiento

1. La aplicación captura una imagen a través de la cámara web
2. La imagen se procesa utilizando el modelo YOLOv5
3. Se aplican las detecciones y se visualizan los resultados
4. Se genera una tabla con el conteo de objetos detectados

## Notas Técnicas

- El modelo utiliza YOLOv5s, que es una versión ligera optimizada para el rendimiento
- Las imágenes se procesan en formato BGR (OpenCV)
- Los resultados se muestran en tiempo real sin necesidad de recargar la página

## Limitaciones

- El rendimiento depende de la capacidad de procesamiento del dispositivo
- La calidad de la detección puede variar según las condiciones de iluminación
- Se requiere una cámara web funcional para su uso

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abra un issue primero para discutir los cambios que le gustaría realizar.

## Licencia

CC
