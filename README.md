# Menú 3D / AR

Base del proyecto para mostrar platos de restaurante en 3D/AR desde el celular.

## Estructura

```
menu-3d-base/
├── index.html      → la página (no hay que tocarla para agregar platos)
├── dishes.json      → aquí se agregan/editan los platos
├── models/          → aquí van tus archivos .glb escaneados
└── README.md
```

## Cómo agregar un plato nuevo

1. Escanea el plato con RealityScan Mobile (o Polycam) y exporta como `.glb`
2. Guarda ese archivo dentro de la carpeta `models/`, por ejemplo `models/mofongo.glb`
3. Abre `dishes.json` y agrega un bloque nuevo, por ejemplo:

```json
{
  "id": "mofongo",
  "name": "Mofongo con camarones",
  "description": "Plátano majado con chicharrón, ajo y camarones al ajillo.",
  "price": "RD$ 650",
  "model": "models/mofongo.glb"
}
```

4. Guarda, sube los cambios a GitHub (`git add`, `git commit`, `git push`) y Render actualiza solo.

## Notas importantes

- El botón de AR **solo funciona en celular** (Chrome en Android, Safari en iPhone), nunca en computadora de escritorio.
- La página necesita estar servida por HTTPS (Render lo hace automático) — no funciona abriendo el archivo directo desde el explorador de Windows.
- Si en algún momento quieres compatibilidad completa con iPhone, exporta también un `.usdz` (RealityScan lo permite) y agrégalo como campo `"ios_model"` en el JSON.

## Siguiente paso pendiente

Reemplazar el plato de muestra (`demo-astronauta`) en `dishes.json` por tu primer plato real escaneado.
