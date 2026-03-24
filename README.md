# 🧪 Análisis de Reacción Química A+B → C+D

## 📌 Tema y Pregunta de Investigación

**Tema:** Predicción y análisis de masa de componentes químicos en una reacción sintética

**Pregunta de investigación:**
> ¿Cómo evoluciona la masa de los reactivos (A y B) y productos (C y D) a lo largo del tiempo en la reacción A+B → C+D, y en qué punto se alcanza el rendimiento máximo?

**Hipótesis:**
> A medida que avanza el tiempo, la masa de los reactivos A y B se consume progresivamente, mientras que la masa de los productos C y D aumenta, hasta alcanzar un punto de equilibrio o rendimiento máximo.

---

## 📂 Fuente de Datos

- **Dataset:** Synthetic Chemical Reaction
- **Fuente:** [Kaggle](https://www.kaggle.com/datasets/cici118/synthetic-chemical-reaction)
- **Formato:** CSV
- **Tamaño:** 200 registros × 5 columnas
- **Reacción modelada:** A + B → C + D
- **Condición inicial:** 1g de A y 1g de B en t=0

### Estructura del dataset

| Columna Excel | Variable | Descripción |
|---|---|---|
| A | Time | Paso de tiempo de la simulación |
| B | Mass A | Masa del reactivo A en cada instante |
| C | Mass B | Masa del reactivo B en cada instante |
| D | Mass C | Masa del producto C en cada instante |
| E | Mass D | Masa del producto D en cada instante |
| F | Rendimiento % | % de formación de C respecto al máximo (calculado) |

### Proceso de limpieza
- El dataset no presentó valores nulos ni celdas vacías.
- Todos los campos numéricos estaban correctamente tipificados como valores continuos.
- No existían duplicados en los registros de tiempo.
- Se añadió la columna F (Rendimiento %) como variable derivada calculada en Excel:
```excel
=(D2/$D$201)*100
```

---

## 🔬 Técnicas de Minería de Datos Aplicadas

### Análisis estadístico descriptivo

| Función Excel | Uso |
|---|---|
| `PROMEDIO` | Media de masa por especie |
| `MAX` / `MIN` | Valores extremos por especie |
| `DESVEST` | Variabilidad de la masa en el tiempo |
| `INDICE` + `COINCIDIR` | Tiempo donde se alcanza el rendimiento máximo |
| `K.ESIMO.MAYOR` | Ranking de valores máximos |

### Variable derivada — Rendimiento %
Se calculó el porcentaje de formación del producto C en cada paso de tiempo respecto al valor máximo final, para medir la eficiencia de la reacción en cada instante.

---

## 📊 Visualizaciones Generadas

1. **Gráfico de líneas** — Evolución de masa de todas las especies (A, B, C, D) en el tiempo
2. **Gráfico de líneas** — Porcentaje de formación del producto C en el tiempo
3. **Gráfico de barras agrupadas** — Comparación de masa inicial vs final por especie

---

## 🤖 Herramientas de IA Utilizadas

- **Claude AI (Anthropic):** Generación y corrección de fórmulas Excel, diagnóstico de errores, interpretación de resultados y redacción de insights accionables.
- **Ideas de Excel:** Detección automática de patrones en los datos y sugerencias de visualizaciones.

> *"Se utilizó Claude AI para identificar relaciones entre variables, corregir errores de escala en los datos y sugerir visualizaciones óptimas para el dashboard."*

---

## ✅ Resultados y Conclusiones

### Resultados clave del rendimiento

| Punto de tiempo | Rendimiento % de C | Interpretación |
|---|---|---|
| t = inicial | 0% | Reacción no ha comenzado |
| t = mitad (paso 100) | 95.41% | Ya se formó el 95% del producto C |
| t = final (paso 200) | 100% | Reacción completamente avanzada |

### Conclusiones

1. La reacción A+B → C+D muestra una formación **muy acelerada** del producto C — antes de la mitad del tiempo ya se alcanzó el **95.41%** del rendimiento máximo.
2. El comportamiento es consistente con una **reacción de orden 1 o 2**, donde la velocidad es máxima al inicio y decrece progresivamente.
3. El producto C alcanza su máximo en el paso final (t=200), con valores del orden de 10¹⁶.
4. El producto D sigue un patrón similar pero con valores aproximadamente la mitad que C.
5. En una aplicación industrial, no sería necesario mantener la reacción por largos períodos dado que el rendimiento se alcanza rápidamente.

---

## ⚠️ Limitaciones y Recomendaciones Futuras

### Limitaciones
- El dataset es **sintético** — los valores no corresponden a mediciones experimentales reales.
- Los valores de masa a escala exponencial dificultan la interpretación directa sin normalización previa.
- No se verificaron supuestos estadísticos formales (normalidad, homocedasticidad).
- El análisis cubre solo las variables de masa, sin incluir temperatura, presión u otras condiciones de reacción.

### Recomendaciones futuras
- **Normalizar** las variables de masa para facilitar la comparación entre especies.
- Aplicar **modelos de regresión** para predecir la masa de C y D en tiempos no observados.
- Migrar el análisis a **Python (pandas, matplotlib, scipy)** para mayor automatización y reproducibilidad.
- Incluir variables adicionales como temperatura y presión para un análisis más completo.
- Validar el modelo con **datos experimentales reales** de laboratorio.

---

## ⚖️ Consideraciones Éticas

- Todas las fórmulas generadas por IA fueron **verificadas manualmente** antes de aplicarlas.
- Los resultados fueron validados comparando con el **comportamiento teórico esperado** de una reacción química.
- Se reconoce explícitamente el uso de **Claude AI** como herramienta de apoyo, sin sustituir el criterio del analista.
- Los datos son de uso público bajo licencia abierta de Kaggle.

---

## 📁 Contenido del Repositorio

```
ExcelIA_[TuNombre]/
├── README.md                        ← Documentación del proyecto
├── Informe_Reaccion_Quimica.docx   ← Informe completo en Word
└── synthetic_chemical_reaction.xlsx ← Dataset analizado en Excel
```

---

*Análisis realizado en Microsoft Excel con apoyo de Claude AI (Anthropic) — Marzo 2026.*

