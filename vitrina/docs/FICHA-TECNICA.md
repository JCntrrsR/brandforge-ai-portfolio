# Ficha técnica

## Stack

| Capa | Tecnología | Por qué |
|---|---|---|
| Framework | **React 18 + Vite** | interfaz reactiva con carga por ruta |
| Lenguaje | **TypeScript** | modelos de marca y plan tipados |
| Estilos | **Tailwind CSS** | sistema visual consistente |
| Estado | **Redux Toolkit + persist** | sesión y proyectos sobreviven a la recarga |
| Datos remotos | **TanStack Query** | caché y estados de carga |
| Rutas | **React Router** | área pública y área privada |
| Formularios | **React Hook Form + esquemas** | validación declarativa |
| Animación | **Framer Motion** | transiciones de interfaz |
| Iconos | **Lucide + Heroicons** | set consistente |

> El proyecto declara además integraciones de autenticación, pagos, IA y analítica. Están
> declaradas como dependencia pero **no conectadas** en esta versión: se documentan como pendientes.

## Tamaño del proyecto

| Métrica | Valor |
|---|---|
| Archivos `.ts` / `.tsx` | 84 |
| Líneas de código | ~16.250 |
| Dependencias declaradas | 46 |
| Rutas | 20+ declaradas · **3 completas** |
| CSS del build | 51 KB |

## Verificación

```
npm run build  →  exit 0 · 0 sourcemaps · CSS 51 KB
npm run test   →  pruebas de componentes
```

## Captura del área privada

El área privada exige sesión. Para documentarla se inyectó una **sesión de demostración** en el
almacenamiento local (usuario, plan y contadores ficticios). No se usó ninguna cuenta real.

## Límites conocidos

| Límite | Motivo |
|---|---|
| Solo 3 áreas terminadas | el resto son rutas declaradas sin contenido |
| IA desconectada | requiere proveedor y presupuesto por generación |
| Pagos simulados | sin claves publicables |
| Datos de demostración | el escaparate no publica información real |

## Qué demuestra al cliente

- Un producto con **área pública y privada** bien separadas por guardas de ruta.
- Arquitectura de estado con persistencia selectiva.
- **Honestidad de alcance**: se muestra lo terminado y se declara lo pendiente, en vez de vender
  pantallas vacías como funcionalidad.
