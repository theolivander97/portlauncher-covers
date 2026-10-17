# Dársena · Portadas

Base de datos de portadas de Dársena, el launcher de juegos porteados.
Se sirve por CDN con jsDelivr:

```
https://cdn.jsdelivr.net/gh/theolivander97/portlauncher-covers@main/<id>.webp
```

| Archivo | Qué es |
|---|---|
| `<id>.webp` | Portada vertical 600×900. `<id>` es el id del juego en el catálogo del launcher |
| `index.json` | `id -> { v, src }`: versión (hash del contenido) y origen de cada portada |
| `overrides.json` | Curación a mano: `id -> "Sistema/Nombre.png"` para forzar una carátula, o `null` para excluirla |
| `manual/` | Portadas subidas a mano (`<id>.png/jpg/webp`); tienen prioridad sobre las automáticas |
| `report.txt` | Juegos del catálogo que aún no tienen portada |

Las portadas se generan con `tools/covers/build-covers.mjs` del repositorio del launcher.
La carga inicial sale de [libretro-thumbnails](https://github.com/libretro-thumbnails/libretro-thumbnails).
Las carátulas pertenecen a sus respectivos propietarios y se usan solo para identificar cada juego en el launcher.

## Contribuir

1. Busca el id del juego en `report.txt`.
2. Añade la imagen a `manual/<id>.png` (preferiblemente la carátula frontal, de al menos 600 px de alto).
3. Abre un pull request.
