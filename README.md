# Piso Perillo – visor 3D

Visor web (solo lectura) del modelo de Blender del piso.

- `escenas/*.glb` – una exportación por cada escena de `perillo.blend` (Original, Opción península, Opción cierre cocina)
- `scenes.json` – lista de escenas, qué objeto pertenece a cada capa y colores de respaldo para los materiales procedurales
- `index.html` – el visor (three.js)

## Verlo en local

Abrir `index.html` con doble clic no funciona (el navegador bloquea la carga del modelo). Desde esta carpeta:

    python3 -m http.server 8000

y abrir http://localhost:8000

## Publicarlo en GitHub Pages

1. Crear un repositorio y subir el contenido de esta carpeta `web/`.
2. En el repo: Settings → Pages → Source: "Deploy from a branch", rama `main`, carpeta `/ (root)`.
3. La web queda en `https://<usuario>.github.io/<repo>/`.

## Actualizar

Al cambiar el modelo en Blender, volver a exportar cada escena a `escenas/<escena>.glb` (File → Export → glTF 2.0, formato .glb, "Visible objects" + "Active scene", sin cámaras ni luces), regenerar `scenes.json` si cambian los objetos, y subir los cambios. Si se añade una escena nueva hay que añadirla también a `scenes.json`.
