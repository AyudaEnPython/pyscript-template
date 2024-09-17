# PyScript Template

[![es](https://img.shields.io/badge/lang-es-yellow.svg)](https://github.com/AyudaEnPython/pyscript-template/blob/master/README.es.md)

# Stack

- [PyScript](https://pyscript.net/): An open source platform for Python in the
  browser.
- [Cirrus](https://cirrus-ui.com/): A modular, responsive, and component centric
  SCSS framework.

## How to use this template

Click on `Use this template` button and then select `Create a new repository`,
or clone this repo to your local machine using
`git clone https://github.com/AyudaEnPython/pyscript-templatte.git`.

Customize the project, replace the favicon, update the setup file with your
desire title and subtitle, etc.

Run the project:

- If your are using VSCode, you can use the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension to run your
  project.
- Alternatively, you can use Python to start a local server. Run the
  following command in your project directory:
  ```bash
  python -m http.server
  ```

## Settings

### Favicon

Add your own favicon (`favicon.ico`) in `assets/images/`

### Title and subtitle

Change title and subtitle in `setup.json` file:

```json
{
  "title": "Your title",
  "subtitle": "Your subtitle"
}
```

### Cirrus Header

To use Cirrus [Header](https://cirrus-ui.com/layout/header), uncomment the
following lines in `assets/js/main.js`:

```js
document.querySelector(".nav-btn").addEventListener("click", function () {
  document.getElementById("header-menu").classList.toggle("active");
  this.classList.toggle("active");
});
```

## PyScript

### Include files

```html
<py-config> [[fetch]] files = ['main.py'] </py-config>
```

This configuration ensures that `main.py` file is fetched and included in your
PyScript environment.

### Handle events

```html
<py-script>
  from pyscript import when, display, document @when("click", "#btn-id") def
  click_handler(event): ...
</py-script>
```

The `@when` decorator is used to bind functions to events. In this case,
`click_handle` is bound to the click event of the button with id `btn-id`.
For more information, read the [official documentation](https://docs.pyscript.net/2024.9.1/api/#pyscriptwhen).
