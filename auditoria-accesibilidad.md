# Reporte de Auditoría de Accesibilidad y UX

**Proyecto:** Voluntariado Juvenil  
**Fecha:** 08/02/2026  
**URL evaluada:** https://voluntariado-xi.vercel.app/  
**Herramienta principal:** Lighthouse 12.8.2 (axe-core 4.11.1)

---

## 1. Resumen Ejecutivo

| Métrica | Valor |
|---------|-------|
| **Puntuación Lighthouse (Accesibilidad)** | 99/100 |
| Total de hallazgos | 2 |
| Críticos | 0 |
| Altos | 0 |
| Medios | 1 |
| Bajos | 1 |

El sitio presenta un nivel de accesibilidad elevado. Se detectó un fallo automático (ARIA) y una mejora recomendada (enlaces genéricos).

---

## 2. Tabla de Hallazgos WCAG 2.1

| Elemento | Fallo detectado | Referencia WCAG 2.1 | Sugerencia de corrección técnica |
|----------|-----------------|---------------------|----------------------------------|
| Sidebar (`aside.sidebar`) | Rol ARIA `navigation` en elemento `<aside>` incompatible. La especificación no permite `role="navigation"` en `aside`. | 4.1.2 Nombre, función, valor (Nivel A) | Sustituir `<aside role="navigation">` por `<nav>`, o usar `<nav>` dentro del aside si se desea mantener la estructura. Ejemplo: `<nav aria-label="Menú de navegación lateral">` |
| Enlaces "Ver más" (sección Novedades) | Texto de enlace genérico repetido cuatro veces. Dificulta navegación por enlaces con lectores de pantalla. | 2.4.4 Propósito de enlaces (Nivel A) | Usar texto descriptivo único: "Ver más sobre Jornada de Limpieza de Playas", "Ver más sobre Programa de Tutorías", etc. O `aria-label` específico en cada enlace. |

### Aspectos que cumplen (verificado por Lighthouse)

- Contraste de colores suficiente
- Imágenes con atributo `alt` correcto
- Documento con `<title>`
- Atributo `lang` en `<html>`
- Jerarquía de encabezados correcta
- Botones con nombre accesible
- Enlaces con nombre discernible (excepto "Ver más" genéricos)
- Estructura de listas correcta

---

## 3. Heurísticas de Experiencia de Usuario (Nielsen)

### 3.1 Visibilidad del estado del sistema

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 1. Visibilidad del estado del sistema | Parcial | El panel de opciones de accesibilidad (tamaño fuente, contraste) ofrece feedback visual. No se verificó feedback en formularios de registro. | Asegurar mensajes de confirmación tras registro; indicadores de carga visibles en transiciones. |

### 3.2 Correspondencia entre sistema y mundo real

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 2. Correspondencia entre sistema y mundo real | Cumple | Lenguaje cercano al usuario (voluntariado, comunidad, certificación). Iconografía Material estándar. | Mantener terminología del dominio de voluntariado. |

### 3.3 Control y libertad del usuario

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 3. Control y libertad del usuario | Cumple | Panel de accesibilidad con "Restablecer configuración". Diálogo con botón cerrar. | Verificar que modales y flujos permitan salir sin completar pasos obligatorios. |

### 3.4 Consistencia y estándares

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 4. Consistencia y estándares | Cumple | Navegación lateral coherente; iconos y etiquetas consistentes. Logo y enlaces siguen convenciones. | Mantener patrones en registro, login e informacion. |

### 3.5 Prevención de errores

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 5. Prevención de errores | Parcial | FAQ orienta al usuario. No se validó formularios de registro. | Validación inline en campos; confirmación antes de acciones destructivas. |

### 3.6 Reconocimiento antes que memorización

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 6. Reconocimiento antes que memorización | Cumple | FAQ visible con preguntas expandibles. Opciones de registro (Voluntario/Organización) claras. Información contextual en cada sección. | Mantener opciones visibles; evitar pasos que requieran memorizar información previa. |

### 3.7 Flexibilidad y eficiencia de uso

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 7. Flexibilidad y eficiencia de uso | Parcial | Panel de accesibilidad (tamaño fuente, alto contraste, reducir movimiento) beneficia a usuarios con necesidades específicas. No se identificaron atajos de teclado. | Considerar atajos para acciones frecuentes; shortcuts opcionales. |

### 3.8 Estética y diseño minimalista

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 8. Estética y diseño minimalista | Cumple | Diseño limpio; cards informativas sin ruido; jerarquía visual clara. | Evitar añadir elementos superfluos. |

### 3.9 Ayuda con errores

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 9. Ayuda con errores | No verificado | No se probaron formularios con errores. | Mensajes de error descriptivos; indicar campo y solución. |

### 3.10 Ayuda y documentación

| Heurística | Cumplimiento | Observaciones | Recomendación |
|------------|--------------|---------------|---------------|
| 10. Ayuda y documentación | Cumple | Sección FAQ completa con preguntas habituales. Enlace "Contáctanos" en registro. Página de información institucional (misión, visión, valores). | Mantener FAQ actualizada; documentación contextual en flujos críticos. |

---

## 4. Matriz de Priorización

| Prioridad | Hallazgo | Acción sugerida |
|-----------|----------|-----------------|
| P3 – Medio | Rol ARIA en `aside` | Sustituir por `<nav>` en próximo ciclo |
| P4 – Bajo | Enlaces "Ver más" genéricos | Mejorar con texto o `aria-label` descriptivo |

---

## 5. Herramientas Utilizadas

- Lighthouse 12.8.2 (modo headless)
- axe-core 4.11.1
- Inspección manual del contenido (home, registro, informacion)

---

## 6. Referencias

- [WCAG 2.1 (es)](https://www.w3.org/WAI/WCAG21/quickref/?lang=es)
- [10 Usability Heuristics for User Interface Design – Nielsen Norman Group](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
- [aria-allowed-role – axe-core](https://dequeuniversity.com/rules/axe/4.10/aria-allowed-role)
