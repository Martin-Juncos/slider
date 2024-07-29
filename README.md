# Slider Project
https://martin-juncos.github.io/slider/
## Descripción

Este proyecto consiste en un control deslizante (slider) que permite a los usuarios desplazarse a través de una serie de elementos, típicamente imágenes o contenido HTML. Es útil para mostrar una galería de imágenes, testimonios, ofertas, etc.

## Funcionalidades

- Desplazamiento automático y manual de elementos.
- Soporte para múltiples sliders en una misma página.
- Controles de navegación (anterior y siguiente).
- Indicadores de progreso o paginación.

## Puesta en Marcha

### Prerrequisitos

Asegúrate de tener instalado Node.js y npm en tu máquina.

### Instalación

1. Clona el repositorio:

   ```bash
   git clone https://github.com/Martin-Juncos/slider.git
   cd slider
   ```

2. Instala las dependencias:
   ```bash
   npm install
   ```

### Uso

1. Para iniciar el servidor de desarrollo:
   ```bash
   npm start
   ```
2. Abre tu navegador y visita `http://localhost:3000` para ver el slider en acción.

### Despliegue

Para construir el proyecto para producción:

```bash
npm run build
```

Los archivos listos para producción se generarán en la carpeta `dist`.

## Lógica del Código

### Estructura de Archivos

- `src/`
  - `index.html`: Archivo principal HTML.
  - `styles.css`: Estilos del slider.
  - `slider.js`: Lógica principal del slider.
  - `app.js`: Inicialización del slider.

### slider.js

Este archivo contiene la lógica del funcionamiento del slider. Los puntos clave incluyen:

1. **Inicialización del Slider**:

   ```javascript
   const slider = document.querySelector(".slider");
   const slides = slider.querySelectorAll(".slide");
   let currentIndex = 0;
   ```

2. **Funciones de Navegación**:

   ```javascript
   function showNextSlide() {
     slides[currentIndex].classList.remove("active");
     currentIndex = (currentIndex + 1) % slides.length;
     slides[currentIndex].classList.add("active");
   }

   function showPrevSlide() {
     slides[currentIndex].classList.remove("active");
     currentIndex = (currentIndex - 1 + slides.length) % slides.length;
     slides[currentIndex].classList.add("active");
   }
   ```

3. **Configuración de Eventos**:

   ```javascript
   document.querySelector(".next").addEventListener("click", showNextSlide);
   document.querySelector(".prev").addEventListener("click", showPrevSlide);
   ```

4. **Auto-deslizamiento**:
   ```javascript
   setInterval(showNextSlide, 3000);
   ```

### app.js

Este archivo se encarga de inicializar el slider:

```javascript
document.addEventListener("DOMContentLoaded", () => {
  const slider = new Slider(".slider");
  slider.init();
});
```

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abre un issue o envía un pull request.

                ©ProfMartin
