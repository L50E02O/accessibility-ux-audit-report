# Reporte de Auditoría de Accesibilidad y UX

**Proyecto:** [Nombre del sitio/aplicación]  
**Fecha:** [DD/MM/AAAA]  
**Auditor:** [Nombre]  
**Entorno evaluado:** [URL o versión]

---

## 1. Resumen Ejecutivo

| Métrica | Valor |
|---------|-------|
| Total de hallazgos | — |
| Críticos | — |
| Altos | — |
| Medios | — |
| Bajos | — |

---

## 2. Tabla de Hallazgos WCAG 2.1

| Elemento | Fallo detectado | Referencia WCAG 2.1 | Sugerencia de corrección técnica |
|----------|-----------------|---------------------|----------------------------------|
| Imagen de logo/banner | Falta de etiquetas Alt o Alt vacío | 1.1.1 Contenido no textual (Nivel A) | Añadir `alt="Descripción significativa"`; para decorativas usar `alt=""` o `role="presentation"` |
| Iconos de navegación | Iconos sin texto alternativo | 1.1.1 Contenido no textual | Incluir texto visible o `aria-label="Descripción"`; verificar lectura por lector de pantalla |
| Botones de acción | Contraste de texto insuficiente (< 4.5:1) | 1.4.3 Contraste mínimo (Nivel AA) | Ajustar colores a ratio ≥4.5:1 (o ≥3:1 para texto grande); usar herramientas como WebAIM Contrast Checker |
| Formulario de login | Campos sin etiquetas asociadas | 3.3.2 Etiquetas o instrucciones (Nivel A) | Usar `<label for="id">` o `aria-labelledby`; evitar placeholders como única etiqueta |
| Menú desplegable | Falta de indicador de foco visible | 2.4.7 Enfoque visible (Nivel AA) | Añadir `outline` o `box-shadow` en `:focus`; evitar `outline: none` sin reemplazo |
| Video/audio | Ausencia de subtítulos o transcripción | 1.2.1 Solo audio/video pregrabado (Nivel A) | Proporcionar subtítulos, transcripción o alternativa de texto |
| Encabezados | Estructura de encabezados incorrecta (h1→h4) | 1.3.1 Info y relaciones (Nivel A) | Usar jerarquía lógica (h1, h2, h3) sin saltos; un solo h1 por página |
| Enlaces | Texto genérico ("clic aquí", "más") | 2.4.4 Propósito de enlaces (Nivel A) | Usar texto descriptivo independiente del contexto; evitar enlaces duplicados idénticos |
| Tablas de datos | Celdas sin encabezados asociados | 1.3.1 Info y relaciones | Usar `<th scope="col">` o `<th scope="row">`; `id` y `headers` para tablas complejas |
| Mensajes de error | Errores no anunciados a lectores de pantalla | 3.3.1 Identificación de errores (Nivel A) | Usar `aria-live="polite"` o `role="alert"`; asociar mensaje con `aria-describedby` |
| Modal/diálogo | No se puede cerrar con Escape | 2.1.2 Sin trampa de teclado (Nivel A) | Implementar cierre con Escape; gestionar foco con `focus-trap` y devolver foco al activador |
| Slider/carrusel | Sin pausa o control de velocidad | 2.2.2 Pausar, detener, ocultar (Nivel A) | Añadir botón de pausa; asegurar que no autoavanza < 5 s o que se puede detener |
| Selector de idioma | Sin `lang` o `lang` incorrecto | 3.1.1 Idioma de la página (Nivel A) | Definir `lang="es"` en `<html>`; usar `lang` en fragmentos en otro idioma |
| Inputs requeridos | Campos obligatorios no identificados | 3.3.2 Etiquetas o instrucciones | Usar `required` + `aria-required="true"`; mensaje de error accesible |
| Cambios de contexto | Envío de formulario al cambiar select | 3.2.2 Al recibir el foco (Nivel A) | Evitar cambios automáticos; ofrecer botón explícito o confirmación previa |

---

## 3. Heurísticas de Experiencia de Usuario (Nielsen)

### 3.1 Visibilidad del estado del sistema

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 1. Visibilidad del estado del sistema | — | El sistema debe informar al usuario en un tiempo razonable sobre lo que ocurre. | Mostrar feedback claro: loaders, confirmaciones, estados de formulario, breadcrumbs. Evitar acciones sin respuesta visual. |

### 3.2 Correspondencia entre sistema y mundo real

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 2. Correspondencia entre sistema y mundo real | — | El lenguaje debe ser familiar al usuario; conceptos del mundo real, no jerga técnica. | Usar terminología del dominio; iconografía reconocible; orden natural de información. |

### 3.3 Control y libertad del usuario

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 3. Control y libertad del usuario | — | Los usuarios cometen errores; deben poder deshacer o salir de situaciones no deseadas. | Incluir "Deshacer", "Cancelar", "Cerrar"; permitir salida de modales/flujos sin pasos obligatorios. |

### 3.4 Consistencia y estándares

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 4. Consistencia y estándares | — | Evitar ambigüedad; seguir convenciones de plataforma e industria. | Mantener patrones coherentes (iconos, colores, etiquetas); seguir convenciones web (logo → inicio, carrito → compra). |

### 3.5 Prevención de errores

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 5. Prevención de errores | — | Diseño que prevenga errores antes de que ocurran. | Validación inline, confirmaciones para acciones destructivas, restricciones claras en campos. |

### 3.6 Reconocimiento antes que memorización

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 6. Reconocimiento antes que memorización | — | Minimizar la carga cognitiva; hacer visible la información necesaria. | Menús, opciones visibles, autocompletado, hints contextuales; evitar exigir recordar pasos previos. |

### 3.7 Flexibilidad y eficiencia de uso

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 7. Flexibilidad y eficiencia de uso | — | Aceleradores para usuarios expertos sin perjudicar a novatos. | Atajos de teclado, favoritos, historial, personalización; mantener flujo simple para principiantes. |

### 3.8 Estética y diseño minimalista

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 8. Estética y diseño minimalista | — | Evitar información irrelevante; cada elemento debe aportar valor. | Reducir ruido visual; priorizar contenido esencial; jerarquía visual clara. |

### 3.9 Ayuda con errores

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 9. Ayuda con errores | — | Mensajes de error en lenguaje natural; indicar el problema y cómo resolverlo. | Errores descriptivos, sugerencias concretas, enlaces a ayuda; no solo códigos técnicos. |

### 3.10 Ayuda y documentación

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 10. Ayuda y documentación | — | Proporcionar documentación fácil de encontrar y orientada a tareas. | FAQs, guías paso a paso, búsqueda; contextualizar la ayuda cerca del flujo. |

---

## 4. Matriz de Priorización

| Prioridad | Criterio | Acción sugerida |
|-----------|----------|-----------------|
| P1 – Crítico | Bloquea el uso a usuarios con discapacidad | Corregir en el siguiente sprint |
| P2 – Alto | Dificulta significativamente la experiencia | Planificar para ciclo próximo |
| P3 – Medio | Mejora notable de usabilidad | Incluir en backlog |
| P4 – Bajo | Refinamiento menor | Evaluar según recursos |

---

## 5. Herramientas Utilizadas

- Lighthouse (Chrome DevTools)
- axe DevTools / axe-core
- WAVE
- [Otras herramientas según el proyecto]

---

## 6. Referencias

- [WCAG 2.1 (es)](https://www.w3.org/WAI/WCAG21/quickref/?lang=es)
- [10 Usability Heuristics for User Interface Design – Nielsen Norman Group](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
