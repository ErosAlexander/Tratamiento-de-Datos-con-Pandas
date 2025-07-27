# 🏠 Proyecto AIRBNB-PRICING

## 📌 Objetivo

Desarrollar un proceso de limpieza y preparación de datos para propiedades de Airbnb, enfocado en:

- Normalización de estructuras de datos complejas  
- Conversión adecuada de tipos de datos  
- Preparación para análisis de precios y características  

---

## 🔍 Procesamiento Realizado

### 🛠️ Normalización de Datos

- Transformación de datos JSON anidados a estructura tabular  
- Desanidamiento de listas en columnas como comodidades y precios  
- Consolidación de 70 registros originales en **3,818 filas** analizables  

---

## ✨ Limpieza y Transformación

| Campo             | Problema                            | Solución Aplicada                     |
|------------------|-------------------------------------|---------------------------------------|
| `precio`         | Formato `"$100.00"`                 | Eliminación de `$` y conversión a `float` |
| `cuota_limpieza` | Valores con comas (`1,000.00`)      | Eliminación de caracteres especiales  |
| `evaluacion_general` | Valores nulos (656 registros) | Imputación con mediana                |
| `descripcion_local` | Texto inconsistente              | Normalización a minúsculas            |

---

## 📊 Tipos de Datos Ajustados

- `max_hospedes`: `string` → `int64`  
- `cantidad_baños`: `string` → `int64`  
- `precio`: `string` → `float64`  
- `cuota_limpieza`: `string` → `float64`  

---

## ⚙️ Tecnologías Utilizadas

- Python 3 como lenguaje principal  
- Pandas para manipulación de datos  
- NumPy para operaciones numéricas  
- Google Colab como entorno de ejecución  

---

## 🚨 Desafíos Técnicos

### Estructura de datos compleja

- Datos anidados con múltiples niveles  
- **Solución:** Uso combinado de `json_normalize` y `explode`  

### Inconsistencias en formatos

- Campos monetarios con distintos formatos  
- **Solución:** Expresiones regulares y transformaciones escalables  

### Manejo de nulos

- 17% de valores faltantes en evaluaciones  
- **Solución:** Análisis de distribución antes de imputación  