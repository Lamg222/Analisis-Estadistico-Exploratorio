# 📊 Análisis Estadístico Avanzado

<div align="center">
  <p><strong>Notebooks de Análisis Exploratorio de Datos y Estadística Inferencial</strong></p>
</div>

---

## 📋 Descripción del Proyecto

Este proyecto contiene una colección completa de notebooks de Jupyter desarrollados en **R** que cubren los aspectos fundamentales del análisis estadístico moderno. Los materiales están diseñados para proporcionar una comprensión profunda de las técnicas estadísticas más importantes en el análisis de datos.

## 📁 Estructura del Proyecto

```
📦 Notebooks/
├── 📊 2.1 Análisis exploratorio de datos en R.ipynb
├── 📈 2.2 Distribuciones de probabilidad en R.ipynb  
├── 🔬 2.3 Principales contrastes de hipótesis en R.ipynb
└── 📖 README.md
```

---

## 📚 Contenido de los Notebooks

### 🔍 **Notebook 2.1: Análisis Exploratorio de Datos en R**

> **Objetivo**: Dominar las técnicas fundamentales para explorar, describir y visualizar conjuntos de datos

#### 📊 **Contenido Principal:**

**1. Introducción al Análisis Exploratorio**
- Diferencias entre análisis descriptivo e inferencial
- Importancia del EDA en el proceso de análisis
- Metodología sistemática de exploración

**2. Tablas y Gráficos de Frecuencias**
- **Tablas unidimensionales**: Frecuencias absolutas y relativas
- **Tablas bidimensionales**: Análisis conjunto de variables
- **Tablas multidimensionales**: Análisis complejo con `apply()`
- **Visualizaciones**:
  - Diagramas de barras (`barplot`)
  - Diagramas de sectores (`pie`)
  - Histogramas avanzados (`hist`)

**3. Medidas de Tendencia Central**
- **Media aritmética** (`mean`)
- **Mediana** (`median`) 
- **Moda** (implementación personalizada)
- Interpretación y casos de uso

**4. Medidas de Posición**
- **Cuantiles** (`quantile`)
- Cuartiles, deciles y percentiles
- Análisis de posiciones relativas
- Visualización con `dotchart`

**5. Medidas de Dispersión**
- **Rango** (`range`, `diff`)
- **Rango intercuartílico** (`IQR`)
- **Varianza** (`var`) y **Desviación típica** (`sd`)
- **Coeficiente de variación**
- Función `summary()` para resúmenes estadísticos

**6. Medidas de Forma**
- **Coeficiente de asimetría** (`skewness` - librería `e1071`)
- **Coeficiente de curtosis** (`kurtosis` - librería `e1071`)
- Interpretación de la distribución de datos

#### 🛠️ **Librerías Utilizadas:**
```r
library(e1071)        # Asimetría y curtosis
library(gmodels)      # CrossTable
library(datasets)     # Datos de ejemplo
```

#### 📊 **Datasets Incluidos:**
- `iris`: Características de flores
- `faithful`: Erupciones del géiser Old Faithful
- Datos sintéticos generados para ejemplos específicos

---

### 📈 **Notebook 2.2: Distribuciones de Probabilidad en R**

> **Objetivo**: Comprender y aplicar las principales distribuciones de probabilidad discretas y continuas

#### 🎯 **Contenido Principal:**

**1. Introducción a las Distribuciones**
- Conceptos de variable aleatoria
- Función de masa vs función de densidad
- Función de distribución acumulada
- Metodología sistemática de análisis

**2. Distribuciones Discretas**

| Distribución | Función R | Parámetros | Aplicación |
|--------------|-----------|------------|------------|
| **Uniforme** | `unif` | a, b | Eventos equiprobables |
| **Binomial** | `binom` | n, p | Éxitos en n ensayos |
| **Geométrica** | `geom` | p | Primer éxito |
| **Hipergeométrica** | `hyper` | N, R, n | Muestreo sin reemplazo |
| **Poisson** | `pois` | λ | Eventos raros |

**3. Distribuciones Continuas**

| Distribución | Función R | Parámetros | Aplicación |
|--------------|-----------|------------|------------|
| **Normal** | `norm` | μ, σ | Fenómenos naturales |
| **Log-Normal** | `lnorm` | μ, σ | Variables positivas |
| **Beta** | `beta` | p, q | Proporciones |
| **Gamma** | `gamma` | a, p | Tiempos de espera |
| **Exponencial** | `exp` | λ | Tiempo entre eventos |

**4. Funciones Estadísticas en R**

Para cada distribución `xxx`:
- `dxxx()`: Función de densidad/masa
- `pxxx()`: Función de distribución (CDF)
- `qxxx()`: Función cuantil (inversa de CDF)
- `rxxx()`: Generación de números aleatorios

#### 💡 **Ejemplos Prácticos:**
- Análisis de supervivencia con log-normal
- Control de calidad con hipergeométrica
- Modelado de llegadas con Poisson
- Presupuestos familiares con Beta
- Teorema Central del Límite visualizado

#### 📊 **Visualizaciones Avanzadas:**
- Curvas de densidad superpuestas
- Comparación de distribuciones
- Simulaciones Monte Carlo
- Verificación de ajuste teórico vs empírico

---

### 🔬 **Notebook 2.3: Principales Contrastes de Hipótesis en R**

> **Objetivo**: Dominar los contrastes de hipótesis más importantes para la toma de decisiones estadísticas

#### 🎯 **Contenido Principal:**

**1. Fundamentos de Contrastes de Hipótesis**
- Hipótesis nula (H₀) vs alternativa (H₁)
- Tipos de contrastes: bilateral y unilateral
- Nivel de significación (α) y p-valor
- Reglas de decisión estadística
- Errores Tipo I y Tipo II

**2. Contrastes de Bondad de Ajuste**

| Test | Función R | Propósito | Supuestos |
|------|-----------|-----------|-----------|
| **Kolmogorov-Smirnov** | `ks.test()` | Ajuste a distribución | Variables continuas |
| **K-S-Lilliefors** | `lillie.test()` | Normalidad | Parámetros estimados |
| **Shapiro-Wilk** | `shapiro.test()` | Normalidad | Muestras pequeñas |

**3. Contrastes Paramétricos**

#### **Supuestos Previos:**
- ✅ **Normalidad**: Test K-S-L (`lillie.test`)
- ✅ **Homogeneidad de varianzas**: Test Bartlett (`bartlett.test`)

#### **Test t-Student (`t.test`)**:

| Tipo | Sintaxis | Aplicación |
|------|----------|------------|
| **Una muestra** | `t.test(x, mu=k)` | H₀: μ = k |
| **Dos muestras independientes** | `t.test(x, y, var.equal=TRUE)` | H₀: μ₁ = μ₂ |
| **Muestras emparejadas** | `t.test(x, y, paired=TRUE)` | H₀: μd = 0 |

**4. Contrastes No Paramétricos**

| Test | Función R | Equivalente Paramétrico | Ventaja |
|------|-----------|------------------------|---------|
| **Signos** | `SIGN.test()` | t-test una muestra | Sin supuesto normalidad |
| **Wilcoxon** | `wilcox.test()` | t-test emparejado | Robusto |
| **Mann-Whitney** | `wilcox.test()` | t-test independiente | Sin normalidad |

**5. Contrastes de Correlación**

#### **Tipos de Correlación:**
- **Pearson** (`cor.test, method="pearson"`): Variables normales
- **Spearman** (`cor.test, method="spearman"`): Datos ordinales
- **Kendall** (`cor.test, method="kendall"`): Muestras pequeñas

#### **Matriz de Correlaciones:**
```r
cor(datos, method="pearson")          # Matriz de correlaciones
pairs.panels()                       # Visualización completa
```

#### 🛠️ **Librerías Especializadas:**
```r
library(nortest)      # Tests de normalidad avanzados
library(BSDA)         # Test de signos
library(MASS)         # Datasets adicionales
library(carData)      # Datos para análisis
library(psych)        # pairs.panels()
```

#### 📊 **Datasets de Ejemplo:**
- `Salaries`: Sueldos de profesores universitarios
- `Cars93`: Características de automóviles
- `birthwt`: Datos de nacimientos
- `iris`: Medidas de flores (incluido en R base)

---

## 🚀 Guía de Uso

### **Prerrequisitos**
```r
# Instalar librerías necesarias
install.packages(c("e1071", "gmodels", "nortest", "BSDA", 
                   "MASS", "carData", "psych", "ggplot2"))
```

### **Orden Recomendado de Estudio**
1. **Notebook 2.1** → Fundamentos de análisis exploratorio
2. **Notebook 2.2** → Comprensión de distribuciones
3. **Notebook 2.3** → Aplicación de tests estadísticos

### **Metodología de Aprendizaje**
1. 📚 **Estudiar la teoría** en cada sección
2. 💻 **Ejecutar los ejemplos** paso a paso  
3. 🔄 **Modificar parámetros** para experimentar
4. 📊 **Interpretar resultados** estadísticos
5. 🎯 **Aplicar a datos propios**

---

## 📈 Conceptos Clave Cubiertos

### **Estadística Descriptiva**
- [x] Medidas de tendencia central, posición y dispersión
- [x] Análisis de forma (asimetría y curtosis)
- [x] Tablas de frecuencias multidimensionales
- [x] Visualizaciones estadísticas avanzadas

### **Distribuciones de Probabilidad**
- [x] 5 distribuciones discretas principales
- [x] 5 distribuciones continuas principales  
- [x] Simulación y verificación empírica
- [x] Teorema Central del Límite

### **Inferencia Estadística**
- [x] Tests de normalidad y bondad de ajuste
- [x] Comparación de medias (paramétricos y no paramétricos)
- [x] Análisis de correlación multivariado
- [x] Interpretación de p-valores y significancia

---

## 🎯 Resultados de Aprendizaje

Al completar estos notebooks, serás capaz de:

✅ **Realizar análisis exploratorio completo** de cualquier dataset  
✅ **Identificar y aplicar distribuciones** de probabilidad apropiadas  
✅ **Ejecutar contrastes de hipótesis** robustos y bien fundamentados  
✅ **Interpretar resultados estadísticos** con rigor científico  
✅ **Visualizar datos** de manera efectiva y profesional  
✅ **Tomar decisiones** basadas en evidencia estadística  

---

## 📞 Información del Proyecto

- **Lenguaje**: R
- **Formato**: Jupyter Notebooks con kernel R
- **Tema**: Análisis Estadístico Avanzado
- **Nivel**: Intermedio-Avanzado
- **Cobertura**: EDA, Distribuciones de Probabilidad, Contrastes de Hipótesis

---

## 📝 Notas Importantes

> ⚠️ **Advertencia**: Estos notebooks requieren una instalación completa de R con las librerías especificadas.

> 💡 **Tip**: Ejecuta las celdas secuencialmente para evitar errores de dependencias.

> 🔍 **Recomendación**: Utiliza `help()` o `?función` para obtener documentación detallada de cualquier función.

---

<div align="center">
  <strong>📊 ¡Feliz Análisis Estadístico! 🎯</strong>
</div>