# Iron Quest ⚔️

Aplicación web gamificada para realizar y seguir entrenamientos de fuerza con mancuernas, barra, kettlebell, agarres para flexiones y esterilla.

## Funciones

- Tres aventuras: Guerrero, Pícaro y Paladín (8 misiones distintas cada una).
- XP por misión (+10) y por jefe final (+0, +10 o +20).
- Temporizador alterno de 45 s de trabajo y 15 s de descanso, con pausa.
- Entrenamientos parciales permitidos, historial y niveles.
- Logros, exportación e importación de progreso en JSON.
- Funciona sin cuenta ni servidor: datos en `localStorage` del navegador.
- PWA instalable y disponible sin conexión tras la primera carga.

## Publicación en GitHub Pages

1. Crea un repositorio en GitHub, por ejemplo `iron-quest`.
2. Sube **todos los archivos y la carpeta `assets/` a la raíz** del repositorio. Puedes usar `Add file > Upload files` o Git.
3. En el repositorio ve a **Settings > Pages**.
4. En **Build and deployment**, elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`; guarda.
5. Abre la URL publicada por GitHub Pages, normalmente `https://TU-USUARIO.github.io/iron-quest/`.
6. En un móvil compatible podrás usar **Instalar app** o la opción **Añadir a pantalla de inicio** del navegador.

Los enlaces son relativos, por lo que también funciona en un repositorio publicado bajo una subruta.

## Probar en local

No abras `index.html` directamente con `file://` si quieres probar la instalación y caché de la PWA. Desde la carpeta de archivos, ejecuta:

```bash
python -m http.server 8000
```

Después visita `http://localhost:8000/`.

## Limitaciones y privacidad

- Los datos se guardan **solo en el navegador y dispositivo actual**. Borrar los datos del navegador puede borrar el progreso. Usa **Exportar progreso** para una copia y **Importar progreso** para pasarlo a otro dispositivo.
- No hay sincronización entre dispositivos, cuentas, notificaciones, reproducción de música ni almacenamiento remoto.
- El temporizador avanza solo mientras la pestaña está activa y el navegador permite ejecutar JavaScript. No es un cronómetro de alta precisión en segundo plano.
- El tiempo de cambio de equipo y la duración real de la rutina pueden variar. Ajusta las cargas según tu técnica y condición física.

## Personalizar ejercicios

Edita el array `ROUTINES` del archivo `app.js`. Cada rutina tiene `id`, `name`, `emoji`, `label`, `description`, `missions` y `boss`. Cada misión es `[nombre, descripción]`.

## Estructura

```text
iron-quest-app/
├── index.html
├── styles.css
├── app.js
├── manifest.webmanifest
├── sw.js
├── assets/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

No requiere dependencias ni instalación de Node.js.
