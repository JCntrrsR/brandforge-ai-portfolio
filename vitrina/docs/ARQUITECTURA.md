# Arquitectura

> Documento de vitrina: explica **cómo está construido** el producto sin publicar el código.

## Decisión principal: una aplicación con área pública y área privada

El producto tiene dos públicos muy distintos: quien llega a evaluarlo y quien ya lo usa a diario.
Se resolvió con **una sola aplicación** y dos capas de acceso:

| Capa | Contenido | Acceso |
|---|---|---|
| Pública | landing, registro, acceso, recuperación | cualquiera |
| Privada | panel, proyectos, editor, IA, plantillas, analítica, facturación | sesión iniciada |

Un **guarda de ruta** decide: sin sesión redirige al acceso; con sesión, entra al panel.

## Estado global

La aplicación mantiene tres bloques de estado:

| Bloque | Qué guarda | Persistencia |
|---|---|---|
| **Usuario** | sesión, plan, preferencias, consumo y límites | sí |
| **Proyectos** | identidades de marca y su versión actual | sí |
| **Interfaz** | paneles abiertos, filtros, avisos | no |

Se persiste solo lo que debe sobrevivir a una recarga. La interfaz se reconstruye: guardar paneles
abiertos produce estados imposibles tras un cambio de versión.

## Capas

```
Presentación (páginas y layouts por área)
      ↓
Dominio (proyectos, editor, plantillas)
      ↓
Estado global (usuario, proyectos, interfaz)
      ↓
Servicios (IA, pagos, datos, analítica)
```

## Decisiones que sostienen el producto

**El área privada nunca se muestra sin sesión.** El guarda está en el árbol de rutas, no dentro de
cada página: una sola condición cubre todas las vistas protegidas.

**Los servicios externos viven en una capa aparte.** Cambiar de proveedor de IA o de pagos no debe
tocar componentes; se cambia el adaptador.

**Los límites del plan son datos, no condiciones sueltas.** El estado del usuario declara cuántos
proyectos, exportaciones y generaciones permite su plan. La interfaz consulta ese dato en vez de
repetir números por el código.

**La exportación es un módulo, no un botón.** Generar un PDF de guía de marca y un paquete de assets
implica composición, tipografías y compresión: se aisló para poder probarlo.

## Flujo actual (lo que sí existe)

```
portada → acceso (sesión demo) → panel con métricas
       → galería de proyectos → editor del proyecto
```

El flujo completo de generación con IA está diseñado pero **no implementado**: las rutas existen
como declaración y se listan como pendientes en la documentación de funcionalidades.

## Rendimiento

| Medida | Valor |
|---|---|
| Dependencias de producción | 46 |
| Sourcemaps en producción | desactivados |
| Carga por ruta | fragmentos separados |
| Estado | persistido solo lo indispensable |

## Construcción

```
npm run build           →  compila y agrupa por ruta
npm run test            →  pruebas de componentes
npm run test:e2e        →  recorridos con Playwright
npm run bundle-analyzer →  composición del paquete
```
