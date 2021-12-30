# Documentación ADD-ON de interpretación gráfica:

## Introducción:

El presente website tiene como objetivo explicar el funcionamiento y los pormenores del desarrollo del ADD-ON de interpretación gráfica. El código utilizado para obtener su funcionamiento, así como los elementos de multimedia utilizados serán adjuntados en el repositorio de GitHub correspondiente (accesible dando clic en "View on GitHub").

Este proyecto fue desarrollado como Trabajo de Integración Curricular previo a la obtención del título de Ingeniero en Tecnologías de la Información, por parte de la Escuela Politécnica Nacional del Ecuador, facultad de Ingeniería Eléctrica y Electrónica.

## Detalles Técnicos:

### Lenguajes de programación manejados:

La aplicación se desenvuelve empleando los siguientes lenguajes de programación:

- googlescript (Google App Scripts).
- javascript.
- HTML5.

### Aplicación:

El ADD-ON se desarrolla sobre la plataforma de Google Spreadsheets, aplicación de G-Suite que permite manejar y compartir hojas de cálculo.

### Arquitectura:

Al desarrollar un ADD-ON sobre Google App Scripts, se tendrá una arquitectura cliente servidor, de modo que todo el procesamiento ha ser manejado en el servidor debe realizarse empleando googlescript, dicho procesamiento se realiza mediante la infraestructura de Google, esto gracias a Google Cloud Platform. La sección enfocada al cliente debe ser desarrollada sobre HTML5 y javascript.

### Requisitos:

Para poder utilizar el ADD-ON se deben cumplir con los siguientes requisitos generales:

1. Poseer una cuenta de G-Suite (Gmail).
2. Utilizar un documento con el ADD-ON instalado o copiar los archivos de desarrollo en el apartado de "APP SCRIPTS" de cualquier hoja de cálculo sobre Google Spreadsheets.
3. El documento utilizado, debe estar guardado como archivo en su Drive.
4. Aceptar todos los permisos que requiere el ADD-ON.

> **Nota:** el apartado 2 será cambiado una vez el proyecto sea calificado pues se publicará el ADD-ON para ser descargado e instalado en el apartado "Complementos" de Google Spreadsheets.

### Compatibilidad:

El ADD-ON fue desarrollado buscando la máxima compatibilidad con la gran mayoría de navegadores actuales. De modo que cualquier navegador actualizado debería ser capaz de ejecutar el mismo sin problemas. Sin embargo, el uso de dos librerías puede afectar la ejecución del ADD-ON, mismas que se observan a continuación:

- _**Web Audio API:**_ se emplean objetos `AudioContext` para generar la sonificación.

<p align="center">
  <img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Compatibilidad_Audio_Context.png" align="center" height="85%" width="85%">
</p>

<p align="center">
<b> Figura 1: </b> Compatibilidad de funciones utilizadas de la Web Audio API (Septiembre 2021) [1].
</p>
<br>

- _**Web Speech API:**_ se emplean objetos `SpeechSynthesisUtterance` para generar un sistema dinámico de texto a voz.

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Compatibilidad_SpeechSynthesis.png" align="center" height="85%" width="85%" >
</p>

<p align="center">
<b> Figura 2: </b> Compatibilidad de funciones utilizadas de la Web Speech API (Diciembre 2021) [2].
</p>
<br>

> **Nota:** se denota que los ADD-ONs sobre todas las aplicaciones de G-Suite aún NO estan disponibles sobre navegadores de dispositivos móviles o presentan problemas con los mismos, por cuánto su uso se asegura específicamente para desktop.

## Instalación del ADD-ON:

Para utilizar el ADD-ON, actualmente se tienen dos posibles métodos de instalación:

### Recibir archivo con ADD-ON Instalado:

Si una persona con acceso de "Editor" o "Propietario" al archivo lo comparte con usted, tendrá acceso al archivo en sí y a las funcionalidades del ADD-ON. Existen dos métodos para compartir un archivo en Google Spreadsheets:

- Compartir mediante interfaz de Google Spreadsheets, la persona dueña o con acceso al archivo debe seguir los siguientes pasos:

> 1. Buscar el botón compartir ubicado en la esquina superior derecha y dar clic en la misma.

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Paso1_comparte_embebido.png" align="center" height="40%" width="40%" >
</p>
<p align="center">
<b> Figura 3: </b> Compartición embebida Spreadsheets (Paso 1).
</p>
<br>

> 2. Colocar el correo de la persona que desea acceso al archivo con el ADD-ON o copiar el enlace y enviarselo.

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Paso2_comparte_embebido.PNG" align="center" height="40%" width="40%" >
</p>
<p align="center">
<b> Figura 4: </b> Compartición embebida Spreadsheets (Paso 2).
</p>
<br>

### Colocar los archivos de configuración en el apartado App Scripts:

> 1. Seleccionar el apartado "App Scripts" en la pestaña "Extensiones".

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Paso1_copia_codigo.PNG" align="center" height="70%" width="70%">
</p>
<p align="center">
<b> Figura 5: </b> Agregar archivos con lógica del ADD-ON (Paso 1).
</p>
<br>

> 2. Agregar 3 archivos HTML y colocar el contenido de los archivos originales. Copiar el contenido del archivo .gs:

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Paso2_copia_codigo.PNG" align="center" height="70%" width="70%">
</p>
<p align="center">
<b> Figura 6: </b> Agregar archivos con lógica del ADD-ON (Paso 2).
</p>
<br>

> **Nota:** se deben copiar 4 archivos; `add_on_logico.gs`, `barra_add_on.html`, `cliente_logico.js.html` y `cliente_interfaz.css.html`. Adicionalmente los nombres deben ser igual a los mencionados.



### Descargar complemento:

Este apartado aún no se encuentra disponible, esto se debe a que el ADD-ON debe entrar por un proceso de revisión prevía a su subida. Una vez el proyecto sea revisado el ADD-ON será subido y su código compartido públicamente

## Carga del ADD-ON:

Una vez pasada la etapa de instalación, deberemos ir al apartado "Complementos", "ADD-ON-SPSH", "Ejecutar Add-On". Tras dar clic en la función de ejecución, la vista de la hoja de cálculo se hará más pequeña y el ADD-ON se insertará en la sección derecha de la aplicación, según se observa:

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Ejecucion_1.PNG" align="center" height="70%" width="70%">
</p>
<p align="center">
<b> Figura 7: </b> Comenzar carga del ADD-ON sobre SpreadSheets.
</p>
<br>

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Ejecucion_2.PNG" align="center" height="90%" width="90%">
</p>
<p align="center">
<b> Figura 8: </b> ADD-ON Cargado correctamente sobre SpreadSheets.
</p>
<br>

## Estructura del ADD-ON:
La estructura del ADD-ON se puede observar a continuación:

<p align="center">
<img src="https://raw.githubusercontent.com/Espejin/ADD-ON-GAS-PUBLIC/main/Imagenes_GHP/Estructura_add_on.PNG" align="center" height="46%" width="46%">
</p>
<p align="center">
<b> Figura 9: </b> Estructura del ADD-ON.
</p>
<br>

- _**Sección 1 (Parámetros rellenables):**_ En esta sección se deben insertar dos valores puntuales, rellenando mediante teclado. El tiempo debe ser llenado en segundos y en la el campo de inserción contiguo se debe insertar el rango de celdas en notación A1. El campo de rango es opcional, sin embargo si este se mantiene vacío se debe seleccionar las celdas con datos utilizando el mouse o con el teclado mediante `SHIFT` + `FLECHAS`.

>  La notación "A1" describe un método de descripción de celdas, constituido por "CeldaInicio:CeldaFin". Ejemplo: "A12:D25".

- _**Sección 2 (Parámetros seleccionables):**_ En esta sección se debe seleccionar entre valores puntuales para configurar el gráfico a ser escuchado. Los campos que se pueden modificar son: tipo de gráfico, tipo de timbre, y manejo de valores faltantes.

-  _**Sección 3 (Compartir Documento):**_ esta sección es opcional y permite compartir el archivo con otra persona, solicitando el correo de la misma, la persona con quién se compartirá el archivo también tendrá acceso al ADD-ON.

-  _**Sección 4 (Botones de acción):**_ en esta opción se encuentran las opciones finales de acción, tras rellenar todos los campos, al dar click en "Sonificación" se genera un gráfico en la hoja de cálculo, a la vez comienza el sonido equivalente al gráfico mencionado, todo esto identificado por una retroalimentación hablada (Text to Speach). El Botón de "Detener" detiene el sonido en curso y el botón "?" da acceso a la documentación del ADD-ON, correspondiente al presente documento.

 &nbsp;&nbsp; Espaciado

## Bibliografía:

[1] 	Mozilla for Developers, «AudioContext,» Mozilla, 14 Septiembre 2021. [En línea]. Available: https://developer.mozilla.org/en-US/docs/Web/API/AudioContext. [Último acceso: 29 Diciembre 2021].

[2] 	Mozilla for Developers, «SpeechSynthesis,» Mozilla, 16 Diciembre 2021. [En línea]. Available: https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis. [Último acceso: 29 Diciembre 2021].

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Espejin/ADD-ON-GAS-PUBLIC/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

