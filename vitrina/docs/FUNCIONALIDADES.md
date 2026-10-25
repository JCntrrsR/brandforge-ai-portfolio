# Funcionalidades

> Qué hace el producto **hoy**, módulo por módulo. Lo no terminado se declara como tal.

## Implementado

### 1. Portada

**Para qué:** que un visitante entienda el producto y decida probarlo.

**Incluye:** propuesta de valor, vista previa de lo que produce, cifras de uso y acceso.

### 2. Acceso y registro

**Para qué:** abrir el área privada sin fricción.

**Incluye:** inicio de sesión, registro, recuperación de contraseña y sesión recordada.

**En la vitrina:** la sesión se simula desde el almacenamiento local con un usuario de ejemplo.

### 3. Panel de trabajo

**Para qué:** que al entrar se sepa qué hacer y cómo va el uso del plan.

**Incluye:** saludo al usuario, métricas (proyectos activos, generaciones de IA, descargas,
colaboradores), accesos rápidos y aviso de límites.

### 4. Proyectos

**Para qué:** cada marca es un proyecto con su historial y su estado.

**Incluye:** galería con filtros por estado y tipo, tarjeta por proyecto y acceso al editor.

### 5. Editor de proyecto

**Para qué:** ajustar la identidad de una marca sin salir del producto.

**Incluye:** edición por módulos de la identidad y guardado del proyecto.

### 6. Sesión y persistencia

**Para qué:** que el trabajo no se pierda al recargar.

**Incluye:** estado del usuario y de los proyectos persistido; la interfaz se reconstruye limpia.

## En construcción (declarado, no disponible)

Estas rutas existen en el producto y **no** ofrecen funcionalidad todavía. Se documentan para no
prometer lo que no hay:

| Módulo | Estado |
|---|---|
| Estudio de IA | interfaz declarada, sin generación conectada |
| Plantillas | pendiente |
| Analítica | pendiente |
| Marketplace | pendiente |
| Facturación | pendiente |
| Colaboración | pendiente |

## Lo que la vitrina **no** hace

- No genera identidades con IA real.
- No cobra ni gestiona suscripciones.
- No sincroniza colaboración entre usuarios.
- No contiene datos reales: la sesión es de demostración.
