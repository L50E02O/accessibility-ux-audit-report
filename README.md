# Accessibility & UX Audit Report

Repositorio de auditorías de accesibilidad web (WCAG 2.1) y evaluación de heurísticas de experiencia de usuario (Nielsen). Incluye reportes documentados y evidencia de análisis automatizado mediante Lighthouse.

## Objetivo

Documentar hallazgos de accesibilidad y usabilidad en sitios web, con una estructura estandarizada que facilite:
- Seguimiento de incidencias
- Priorización de correcciones
- Validación de cumplimiento WCAG 2.1
- Evaluación de heurísticas de usabilidad

## Estructura del Proyecto

```
accessibility-ux-audit-report/
├── README.md
├── auditoria-accesibilidad.md   # Reporte principal de auditoria
└── .gitignore
```

## Contenido del Reporte

Cada auditoría incluye:

| Sección | Descripción |
|---------|-------------|
| Resumen ejecutivo | Puntuación Lighthouse, métricas y hallazgos |
| Tabla WCAG 2.1 | Elemento, fallo, referencia y sugerencia de corrección |
| Heurísticas Nielsen | Evaluación de las 10 reglas de usabilidad |
| Matriz de priorización | Criterios P1-P4 para planificación |

## Sitio Auditado

- **URL:** https://voluntariado-xi.vercel.app/
- **Proyecto:** Voluntariado Juvenil
- **Resultado Lighthouse (Accesibilidad):** 99/100

Ver detalles completos en [auditoria-accesibilidad.md](./auditoria-accesibilidad.md).

## Ejecutar Auditoría (Lighthouse)

Requiere Node.js y Chrome/Chromium instalados.

```bash
npx lighthouse https://voluntariado-xi.vercel.app/ \
  --output=json \
  --output-path=./lighthouse-report.json \
  --only-categories=accessibility \
  --chrome-flags="--headless --no-sandbox"
```

El reporte JSON generado se excluye del repositorio mediante `.gitignore`.

## Herramientas Utilizadas

- **Lighthouse** – Auditoría automatizada de accesibilidad
- **axe-core** – Motor de reglas WCAG integrado en Lighthouse
- **Inspección manual** – Revisión de contenido, flujos y heurísticas

## Referencias

- [WCAG 2.1 Quick Reference](https://www.w3.org/WAI/WCAG21/quickref/?lang=es)
- [10 Usability Heuristics – Nielsen Norman Group](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
