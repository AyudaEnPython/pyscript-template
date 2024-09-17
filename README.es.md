# Plantilla de PyScript

[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/AyudaEnPython/pyscript-template/blob/master/README.md)

## Stack

- [PyScript](https://pyscript.net/): Una plataforma de código abierto para
  Python en el navegador.
- [Cirrus](https://cirrus-ui.com/): Un marco SCSS modular, responsivo y
  centrado en componentes.

## Cómo usar esta plantilla

Clic en el botón `Usar esta plantilla` y después seleccionar `Crear un nuevo repositorio`,
o clona este repositorio en tu máquina local usando
`git clone https://github.com/AyudaEnPython/pyscript-template.git`.

Personaliza el proyecto, reemplaza el favicon, actualiza el archivo de
configuración con el título y subtítulo que desees, etc.

Ejecuta el proyecto:

- Si estas usando VSCode, puedes usar la extensión [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) para ejecutar
  tu proyecto.
- Alternativamente, puedes usar Python para iniciar un servidor local.
  Ejecuta el siguiente comando en tu directorio del proyecto.
  ```bash
  python -m http.server
  ```

## Configuraciones

### Favicon

Agrega tu propio favicon (`favicon.ico`) en `assets/images/`

### Título y subtítulo

Cambia el título y subtítulo en el archivo `setup.json`:

```json
{
  "title": "Tu título",
  "subtitle": "Tu subtítulo"
}
```

### Cirrus Headers

Para usar Cirrus [Header](https://cirrus-ui.com/layout/header), descomenta las
siguientes líneas en `assets/js/main.js`:

```js
document.querySelector(".nav-btn").addEventListener("click", function () {
  document.getElementById("header-menu").classList.toggle("active");
  this.classList.toggle("active");
});
```

## PyScript

### Incluir archivos

```html
<py-config> [[fetch]] files = ['main.py'] </py-config>
```

Esta configuración asegura que le archivo `main.py` se obtenga e incluya en tu
entorno PyScript.

### Manejar eventos

```html
<py-script>
  from pyscript import when, display, document @when("click", "#btn-id") def
  click_handler(event): ...
</py-script>
```

El decorador `@when` es usado para vincular funciones a eventos. En este caso,
`click_handler` está vinculado al evento de clic del botón con id `btn-id`.
Para mayor información, leer la [documentación oficial](https://docs.pyscript.net/2024.9.1/api/#pyscriptwhen).
