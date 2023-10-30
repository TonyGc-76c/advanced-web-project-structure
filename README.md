# Estructura de un proyecto web

## Proyecto avanzado

### Tree

```
advanced-web-project-structure/
│
├─ public/
│  ├─ assets/
│  │  ├─ icons/
│  │  ├─ img/
│  │  ├─ fonts/
│  │  └─ media/
│  │     ├─ audio/
│  │     └─ video/
│  ├─ css/ 
│  ├─ js/ 
│  │  └─ scripts-min.js
│  └─ index.html o +html's
│
└─ src/ 
   ├─ assets/
   ├─ scss/
   │  ├─ base/
   │  │  ├─ _base.scss
   │  │  └─ _normalize.scss
   │  ├─ blocks/
   │  │  └─ _buttons.scss
   │  ├─ config/
   │  │  ├─ _colors.scss
   │  │  └─ _fonts.scss
   │  ├─ helpers/
   │  ├─ mixins/
   │  │  └─ _breakpoints.scss
   │  ├─ pages/ 
   │  └─ styles.css 
   ├─ database/
   │  └─ archivo-bd.sql
   ├─ docs/
   │  └─ manual.md
   ├─ js/
   │  ├─ helpers/ 
   │  ├─ modules/ 
   │  └─ index.js
   └─ views/
      ├─ config/
      ├─ includes/
      │  └─ button.pug
      ├─ mixins/
      ├─ pages/
      ├─ templates/
      └─ index.html
```

### Carpetas

La carpeta [public]() es la que contiene todo el [entorno de distribución]() y aquí se encuentran todos los archivos ya procesados (es decir, archivos comprimidos, mimificados, sin comentarios ni espacios innecesarios) listos para la entrega final del proyecto y para subirlos al servidor.

- La carpeta [assets]() es la que contiene todos los archivos extra al código como las imagenes, audios, video no disponibles publicamente en internet, solo propios del proyecto
  
  - La carpeta [icons]() contiene los iconos unicos propios del proyecto, las extensiones para estos archivos deben ser en .png o .svg
    
  - La carpeta [img]() tiene todas las imagenes utilizadas para banners, galerías, etc. utilizadas para el proyecto.
    
  - La carpeta [fonts]() tiene las fuentes y tipografía unicas del proyecto, ya sean estas creadas o compradas para utilizarlas en el sitio web.
    
  - La carpeta [media]() sera la carpeta relativa a los archivos multimedia como adios y videos, dentro de esta tendra una carpeta por cada tipo de archivo.
    
    - [audio]()
      
    - [video]()
      
- La carpeta [css]() o [scss]() enteramente contiene solo archivos utilizados para los estilos del frontend, al ya estar procesado se encuentra solo un [styles.css]() de una sola línea.
  
- La carpeta [js]() contiene los archivos de javascript, que al ya estar procesados se encuentra solo uno llamado [scripts-min.js]() con todas las funciones concatenadas.
  
- Finalmente el archivo [index.html]() y el resto de los archivos [html]() de las paginas del sitio.
  

La carpeta [dev]() o [src]() comunmente es utilizada por herramientas para la estructuración de proyectos, aquí es donde se encuentra el [entorno de desarrollo]() y es donde se estara trabajando con los archivos brutos sin procesar.

- La carpeta [assets]() sera igual que la carpeta encontrada en [public](), sin embargo en esta, todos los archivos aún estan sin ser tratados ni procesados.
  
- La carpeta [css]() o [scss]() enteramente contiene todos los archivos relativos a los html utilizados para el proyecto.
  
  - La carpeta [base]() contendra:
    
    - El archivo [_base.scss]() contendra los estilos generales del proyecto como el body, titulos, enlaces, imagenes, etc., en este archivo solo se trabajara con etiquetas comunes al proyecto.
      
    - El archivo [_normalize.scss]() es un archivo que importara la configuración del [scss]() directamente de internet para los archivos [css]().
      
  - La carpeta [blocks]() mantendra todos aquellos elementos que se repiten en la pagina como botones, galerias, formularios, logos, icono menu, etc.
    
    - Un ejemplo podría ser el archivo [_buttons.scss]() que solo estara dedicado a este tipo de elementos, apartir de aqui se utilizan clases y debera haber una hoja para cada tipo de elemento.
      
  - La carpeta [config]() contendra los archivos para configuración del proyecto como las variables, fuentes, colores, etc.
    
    - Podría haber un archivo [_colors.scss]() que mantendra solo eso los colores para cada elemto de las páginas de l proyecto.
      
    - Podría haber un archivo [_fonts.scss]() que de igual manera solo se dedicara a los estilos de las fuentes.
      
  - La carpeta [helpers]() tendra los archivos de ayuda como funciones de otros proyectos que se pedan volver a usar en este, un ejemplo sería un reset de estilos para las listas.
    
  - La carpeta [mixins]() mantendra los archivos responsables para el diseño responsive como los breakepoints.
    
    - El archivo [_breakpoints.scss]() tiene las funciones de diseño responsive como grid o flexbox.
      
  - La carpeta [pages]() tendra estilos unicos para paginas que lo necesiten como archivos con configuracion especial.
    
    - Un ejemplo para un archivo aquí, sería que si en la página contacto hay un formulario que bien podria ser un bloque, este no tendra estilos particulares.
      
    - Otro ejemplo podía ser una galeria de fotos con un banner que en un bloque de galería general no tendría.
      
  - En este archivo [styles.css]() se importaran todos los scss y sera el unico archivo que importa compilar. para importar hojas en este archivo se debe hacer de la siguiente forma.
    ```
    @import "base/normalizer";
    
    /* También se puede hacer de la siguiente forma*/
    
    @import "base/base",
     "base/normalizer";```
    
- La carpeta [database]() tendra el o los archivos [.sql]() enfocados a la base de datos, procedimientos y triggers.
  
- La carpeta [docs]() concentra todos los archivos informativos al contenido del proyecto, su funcionamiento, procedimientos, funciones y el manual de navegacion de usuaios, generalmente estos archivos se encuentran con la extención [.doc](), [.txt]() o [.md]().
  
- La carpeta [js]() contiene los archivos de javascript, que contienen las acciones o funciones que haran ciertos componentes del sitio.
  
  - La carpeta [helpers]() tiene todos los archivos con funciones de ayuda, funciones común a todas las páginas.
    
  - La carpeta [modules]() matiene archivos comunes a todas las páginas como es el caso de los block de css o includes de pug (ejemplo, llamada de formularios).
    
  - El archivo [index.js]() sera donde se haran los imports de todos los [js]().
    
- La carpeta [views]() contendra todos los archivos de las paginas del proyecto ya sean en html o pug.
  
  - La carpeta [config]() guarda archivos de variables propias del proyecto, puede ser el guardar las paginas en un array y luego recorrerlo.
    
  - La carpeta [includes]() estaran los elementos que se van a repetir en html como botones, menus, formularios.
    
    - El archivo [buttons.pug]() es un ejmplo de estos elementos.
      
  - La carpeta [mixins]() estaran los archivos con funciones que crean o generan cosas, html (ejemplo, tarjeta de usuario).
    
  - La carpeta [pages]() guarda cada página del sitio.
    
  - La carpeta [templates]() guarda archivo o archivos comunes para todas las paginas en todo caso aqui podría haber archivos con extensiones [.pug]().
    
  - El arcivo [index.html]()
    

> **NOTA:** Para optimizar el código css se puede hacer uso de la herramineta [Gulp](https://gulpjs.com/) y para transpilar el código de js se puede utilizar [babel]().
> 
> El "[_]()" guión bajo o barra baja, indica que son archivos parciales, archivos que no se compilan y que se importan en otro sitio.

### Créditos

Este proyecto fue inspirado en la metodología utilizada por @DorianDesings

Github: [github.com/DorianDesings](github.com/DorianDesings)

YouTube: [youtube.com/@DorianDesings/featured](https://www.youtube.com/@DorianDesings/featured)

Video de YouTube: [youtube.com/watch?v=SBgVxnEHQR4](https://www.youtube.com/watch?v=SBgVxnEHQR4)
