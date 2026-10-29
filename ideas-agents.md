# Propuesta: Incorporación de Rendimiento y Core Web Vitals en AGENTS.md

Este documento borrador analiza cómo y por qué incorporar pautas de **Core Web Vitals** en la plantilla de `AGENTS.md`, preservando su carácter **genérico y portable** entre distintos tipos de proyectos (backend, frontend, CLIs, etc.).

---

## 1. ¿Qué es Core Web Vitals y por qué importa?

**Core Web Vitals (CWV)** no es una herramienta instalable, sino un conjunto de **métricas estándar definidas por Google** para medir la calidad real de la experiencia de usuario (UX) en la web. Se miden en pruebas de laboratorio (Lighthouse, PageSpeed) y con usuarios reales (Chrome User Experience Report - CrUX).

Las tres métricas fundamentales son:

1. **LCP (Largest Contentful Paint) - Velocidad de percepción de carga**
   * *Qué mide:* Cuánto tarda en renderizarse el contenido visual principal (el título hero, la tabla principal o la imagen destacada).
   * *Objetivo:* $\le$ 2.5 segundos.
   * *Causa común en frontend:* Cascadas de peticiones (waterfalls), bundles JS enormes o fuentes web bloqueantes.

2. **INP (Interaction to Next Paint) - Fluidez de respuesta e interactividad**
   * *Qué mide:* El tiempo que tarda la interfaz en responder visualmente tras una interacción (click en un botón, escribir en un buscador, abrir un modal).
   * *Objetivo:* $\le$ 200 milisegundos.
   * *Causa común en frontend:* Tareas pesadas síncronas en el hilo principal durante un evento, o re-renders innecesarios de árboles de componentes gigantes.

3. **CLS (Cumulative Layout Shift) - Estabilidad visual**
   * *Qué mide:* Cuántos saltos o desplazamientos sufre la pantalla mientras se cargan imágenes, banners o datos asíncronos.
   * *Objetivo:* $\le$ 0.1 (casi imperceptible).
   * *Causa común en frontend:* Insertar contenido asíncrono o imágenes sin reservar dimensiones fijas o `aspect-ratio` previo (el contenido "empuja" al resto de la página).

---

## 2. El dilema de la portabilidad: ¿por qué debe ser condicional?

`AGENTS.md` está concebido para ser un estándar corporativo/institucional compartido entre múltiples repositorios (APIs, workers, CLIs, frontends).

* Si se agrega una regla de Core Web Vitals de forma incondicional, **se agrava el sesgo frontend del archivo** (a una API en Go o una librería en Node no le interesan el CLS ni el LCP).
* La solución limpia, idéntica a la adoptada para *Accesibilidad* (`"si el proyecto tiene interfaz de usuario..."`), es redactar la pauta con un **prefijo condicional**. De este modo, en proyectos que no sean web, el agente ignora la regla por completo.

---

## 3. Borrador propuesto con condicional (para evaluar en la plantilla central)

Ubicación sugerida: Dentro de `### Estilo del código`, inmediatamente después de la regla de *Accesibilidad*.

```markdown
- **Rendimiento web y Core Web Vitals**: si el proyecto es una aplicación web con interfaz de usuario, optimizá por defecto para mantener la carga rápida, la respuesta fluida y la pantalla visualmente estable:
  - no generes saltos de pantalla (CLS): reservá dimensiones explícitas o `aspect-ratio` para imágenes, multimedia y contenedores asíncronos, y usá esqueletos de carga con la altura estimada del contenido para que nada salte al llegar los datos;
  - no bloquees la interacción del usuario (INP): mantené livianos los manejadores de eventos (clicks, inputs, teclas); no ejecutes transformaciones pesadas síncronas en el hilo principal durante una interacción (diferilas, usá debounce o las herramientas de concurrencia del framework);
  - evitá cascadas de peticiones (LCP): no encadenes llamadas asíncronas si pueden resolverse en paralelo, y cargá bajo demanda los componentes o librerías pesadas que no se usen en el render inicial.
```

---

## 4. Ventajas de este formato

1. **Portable:** No rompe proyectos backend, APIs ni librerías.
2. **Accionable:** No dice simplemente *"hacé que sea rápido"*, sino que da los 3 hábitos técnicos concretos que previenen los problemas más comunes.
3. **Agnóstico a librerías:** No nombra React, Vue ni frameworks específicos (menciona *"herramientas de concurrencia o debounce del framework"*, *"llamadas asíncronas"*), cumpliendo la regla de que fuera de `## Propio de este proyecto` debe ser neutral.
