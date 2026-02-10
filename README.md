# Predicción de delitos en CABA (2021–2023)

## Objetivo del proyecto
El objetivo de este proyecto es analizar patrones espacio-temporales de la actividad delictiva
en la Ciudad de Buenos Aires y desarrollar modelos de Machine Learning para predecir la cantidad
de delitos por comuna, día de la semana y franja horaria.

El proyecto combina análisis exploratorio de datos (EDA) y modelado predictivo, con foco en la
interpretación de resultados y en la comparación entre distintos enfoques de modelado.

---

## Dataset
Se utilizan registros de delitos ocurridos en la Ciudad de Buenos Aires entre los años 2021 y 2023.
Cada registro representa un evento delictivo, con información temporal, espacial y del tipo de delito.

Los archivos de datos originales no se incluyen en el repositorio por razones de tamaño.

---

## Análisis Exploratorio de Datos (EDA)
Durante el EDA se analizaron patrones temporales, espaciales y por tipo de delito. Entre los principales
hallazgos se destacan:

- Incremento en la cantidad total de delitos a lo largo del período analizado.
- Fuerte concentración de delitos en determinadas comunas, especialmente en la comuna 1.
- Predominio de robos y hurtos, que representan aproximadamente el 70% del total de los delitos.
- Mayor actividad delictiva en franjas horarias de alta circulación de personas, particularmente entre
  las 17 y las 20 horas.

El análisis también evidenció una alta variabilidad en la cantidad de delitos incluso bajo las mismas
condiciones, lo que anticipa un límite natural al poder predictivo de los modelos.

---

## Feature Engineering
Se construyeron variables temporales y espaciales para capturar patrones relevantes del fenómeno
delictivo, entre ellas:

- Variables temporales: año, mes, día de la semana y franja horaria.
- Variable espacial: comuna.
- Variable objetivo `cantidad`, obtenida como el conteo de delitos por combinación de tiempo y espacio.

Durante este proceso se realizó una limpieza y unificación de la variable comuna, debido a la presencia
de múltiples nomenclaturas para una misma categoría.

---

## Modelado
Se entrenaron y compararon distintos modelos de regresión:

- Regresión Lineal (modelo base)
- Random Forest
- Random Forest ajustado
- Gradient Boosting
- XGBoost

Los modelos basados en árboles mostraron un desempeño muy superior al baseline lineal. XGBoost fue
seleccionado como modelo final por lograr el mejor balance entre desempeño y estabilidad.

### Resultados destacados
- R² en test 0.49
- R² promedio en validación cruzada 0.41
- Las variables más relevantes fueron la comuna y la franja horaria.

---

## Conclusiones
El proyecto muestra que el delito presenta patrones espaciales y temporales claros, especialmente
asociados a la ubicación y al horario. Sin embargo, la alta variabilidad observada sugiere la influencia
de factores no observados, lo que limita el poder explicativo máximo de los modelos.

Los resultados obtenidos son consistentes con la naturaleza del fenómeno y reflejan un enfoque realista
y robusto del problema.

---

## Próximos pasos
Como líneas de trabajo futuro se propone:

- Incorporar datos de años más recientes para evaluar cambios estructurales en los patrones delictivos.
- Integrar visualizaciones geoespaciales, como mapas de calor por comuna y franja horaria.
- Evaluar enfoques específicos para series temporales.

---

## Tecnologías utilizadas
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- XGBoost
