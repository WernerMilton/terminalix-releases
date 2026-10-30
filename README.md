# Terminalix Releases

Catálogo público y firmado de los plugins de [Terminalix](https://github.com/WernerMilton/terminalix).
Terminalix lo descarga desde acá para el marketplace de Extensiones.

```
marketplace/v2/index.json                    catálogo
marketplace/v2/index.sig                     firma Ed25519 de los bytes exactos de index.json
marketplace/v2/plugins/<nombre>/<sha256>.zip  cada versión, direccionada por contenido
```

- **Firmado:** Terminalix trae las claves públicas y rechaza el catálogo si la firma no
  coincide, si venció (`expires_at`) o si la revisión es más vieja que la que ya vio.
- **Verificado:** cada ZIP se valida por tamaño y SHA-256 antes de instalarlo.
- **Sin permisos automáticos:** instalar un plugin nunca otorga permisos; el usuario
  los aprueba uno por uno.
- **Inmutable:** los ZIP no se borran ni se reescriben; una versión nueva es un ZIP nuevo.

No contiene código fuente propio: este repo sólo recibe lo que publica
`scripts/publish.mjs` desde el repo de plugins.
