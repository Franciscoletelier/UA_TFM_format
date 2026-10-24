# Plantilla de TFM — Máster en Economía Aplicada (UA)

Plantilla en Quarto para el Trabajo de Fin de Máster de la Facultad de
Ciencias Económicas y Empresariales de la Universidad de Alicante.

La portada reproduce la plantilla oficial `portada-tfm-economicas` y el
formato sigue la normativa *Normativa y redacción del TFM del Máster en
Economía Aplicada* (CID, curso 2025-26).

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `TFM.qmd` | El contenido del trabajo. Es el único archivo que editas a diario. |
| `_quarto.yml` | Formato del PDF: márgenes, tipografía, interlineado, numeración. |
| `before-body.tex` | La portada. Toma los datos del encabezado de `TFM.qmd`. |
| `references.bib` | Tu bibliografía en formato BibTeX. |
| `apa.csl` | Estilo de citas Harvard-APA. |
| `images/portada-ua.jpg` | Imagen oficial de la portada. No la modifiques. |

## Requisitos

1. [Quarto](https://quarto.org/docs/get-started/) 1.4 o superior.
2. Una distribución de LaTeX con XeLaTeX. Si no tienes ninguna, instala
   TinyTeX desde la terminal con `quarto install tinytex`.

## Cómo generar el PDF

**En RStudio:** abre `TFM.qmd` y pulsa **Render**.

**En VSCode o en la terminal:**

```bash
quarto render TFM.qmd --to pdf
```

El PDF aparece en la carpeta `_output/`.

> La vista previa del navegador (`quarto preview`) muestra la versión HTML, en
> la que la portada no aparece porque está escrita en LaTeX. Para ver el
> resultado real, abre el PDF de `_output/`.

## Cómo rellenar la portada

Todos los datos de la portada salen del encabezado YAML de `TFM.qmd`. Edita
solo los valores entre comillas:

```yaml
title: "TÍTULO DEL TRABAJO"
author:
  - "Nombre y Apellidos del Estudiante"
tutor: "Nombre y Apellidos del Tutor o Tutora"
departamento: "DE ANÁLISIS ECONÓMICO APLICADO"
master: "ECONOMÍA APLICADA"
curso: "2025 - 2026"
lugarfecha: "San Vicente del Raspeig, junio de 2026"
```

El texto de la portada va en mayúsculas en la plantilla oficial, salvo los
nombres de las personas y la línea del lugar y la fecha.

## Estructura del trabajo

El orden de `TFM.qmd` sigue el que indica la normativa:

1. Portada
2. Resumen, palabras clave y códigos JEL, en español y en inglés (segunda página)
3. Índice, índice de figuras e índice de tablas
4. Introducción
5. Antecedentes y marco teórico
6. Objetivos
7. Metodología
8. Desarrollo, con la discusión de los resultados
9. Conclusiones
10. Bibliografía
11. Anexos

Si tu trabajo no lleva figuras ni tablas, borra las cuatro líneas de
`\listoffigures` y `\listoftables` que hay en `TFM.qmd`.

## Formato que aplica la plantilla

Estos valores vienen de la normativa (p. 7 y 17) y ya están configurados:

| Requisito | Valor |
|---|---|
| Papel | DIN A4 |
| Margen superior e inferior | 2,5 cm |
| Margen izquierdo y derecho | 3 cm |
| Tipo de letra | 12 puntos |
| Interlineado | 1,5 |
| Alineación | Justificada |
| Numeración | Inferior, centrada, en todas las páginas |
| Citas | Harvard-APA |
| Resumen | Máximo 300 palabras, en español y en inglés |
| Palabras clave | Máximo 5, en español y en inglés |
| Extensión mínima | 40 hojas (no se comprueba de forma automática) |

## Citas y bibliografía

Añade tus fuentes a `references.bib` y cítalas en el texto:

- `[@clave]` produce «(Apellido, 2020)».
- `@clave` produce «Apellido (2020)».

La bibliografía se genera sola en el apartado correspondiente, ordenada
alfabéticamente. Solo aparecen las fuentes que hayas citado; si quieres
incluir una que no citas, añade `nocite: |` seguido de `@clave` en el YAML.

## Figuras y tablas

La normativa exige que lleven título, numeración y la fuente de los datos, y
que se mencionen en el texto. El patrón a seguir:

````markdown
```{r}
#| label: fig-paro
#| fig-cap: "Tasa de paro por comunidad autónoma, 2024"

plot(...)
```

*Fuente:* elaboración propia a partir de los datos del INE.
````

Para referirte a ellas en el texto escribe `@fig-paro` o `@tbl-paro`, y Quarto
pone el número correcto automáticamente.
