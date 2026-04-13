MoviePy: Edición de Videos con Python
1
2
3
MoviePy es una biblioteca de código abierto para Python que permite realizar edición de video de manera no lineal. Con esta herramienta, puedes cortar, unir, rotar, añadir texto, cambiar la velocidad y aplicar efectos personalizados a tus videos. Es compatible con formatos como MP4, AVI, GIF, entre otros, y funciona en Windows, macOS y Linux.

Instalación

Para instalar MoviePy, utiliza el siguiente comando en tu terminal:

pip install moviepy
Copiar
Si necesitas funcionalidades adicionales como manipulación avanzada de videos o textos, puedes instalar dependencias opcionales:

pip install moviepy[optional]
Copiar
Ejemplos de Uso

Cargar un Video

Para trabajar con un video, primero debes cargarlo en un objeto VideoFileClip:

from moviepy.editor import VideoFileClip

video = VideoFileClip("mi_video.mp4")
Copiar
Cortar un Video

Puedes extraer un segmento específico del video usando el método subclip():

corte = video.subclip(10, 20) # Del segundo 10 al 20
corte.write_videofile("video_cortado.mp4")
Copiar
Unir Videos

Para combinar varios videos en uno solo, utiliza concatenate_videoclips():

from moviepy.editor import concatenate_videoclips

video1 = VideoFileClip("video1.mp4")
video2 = VideoFileClip("video2.mp4")
video_final = concatenate_videoclips([video1, video2])
video_final.write_videofile("video_combinado.mp4")
Copiar
Añadir Texto

Puedes superponer texto en el video con TextClip y CompositeVideoClip:

from moviepy.editor import TextClip, CompositeVideoClip

texto = TextClip("¡Hola Mundo!", fontsize=70, color='white').set_duration(10).set_position('center')
video_con_texto = CompositeVideoClip([video, texto])
video_con_texto.write_videofile("video_con_texto.mp4")
Copiar
Cambiar Velocidad

Para acelerar o ralentizar un video, usa la función fx:

from moviepy.editor import vfx

video_acelerado = video.fx(vfx.speedx, 2) # Acelera 2 veces
video_acelerado.write_videofile("video_acelerado.mp4")
Copiar
Rotar un Video

Puedes rotar un video con el método rotate():

video_rotado = video.rotate(90) # Rota 90 grados
video_rotado.write_videofile("video_rotado.mp4")
Copiar
Extraer Audio

Para extraer el audio de un video y guardarlo como MP3:

audio = video.audio
audio.write_audiofile("audio_extraido.mp3")
Copiar
Ventajas

MoviePy es ideal para tareas rápidas de edición que en otros programas podrían requerir más tiempo o recursos. Además, su integración con Python permite combinar la edición de video con análisis de datos o inteligencia artificial.

Si buscas una herramienta flexible y potente para editar videos con Python, MoviePy es una excelente opción.
