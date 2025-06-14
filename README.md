# TelecomX_LATAM
Challenge TelecomX_LATAM - Alura LATAM

## **Objetivo del Análisis ⭐**

El objetivo de este análisis es comprender y divulgar las causas por las cuales la empresa TelecomX está experimentando una alta tasa de evasión de clientes. La evasión representa pérdidas monetarias para la empresa, ya que no recibe ingresos por una porción del servicio que presta mensualmente.

## **Limpieza y Procesamiento de Datos 🧹**

Para realizar las tareas de limpieza y procesamiento de los datos, se utilizaron las librerías **Pandas** y **Numpy**, junto con la documentación oficial y diversas fuentes en línea para obtener información adicional.

### **Importación de los Datos**

Se utilizó la función `read_json()` de **Pandas** para importar los datos.

### **Limpieza y Procesamiento**

1. **Muestra Parcial de los Datos**: Usé `head()` para obtener una muestra parcial del dataset y ver que las columnas contienen objetos **JSON**.
2. **Creación de un Nuevo DataFrame**: Creé un nuevo dataframe denominado "df\_json" seleccionando columnas con valores en formato JSON.
3. **Normalización de Columnas**: Utilicé un ciclo `for` para recorrer las columnas y normalizarlas, tratándolas como una tabla. Las columnas normalizadas fueron añadidas al dataframe original.
4. **Eliminación de Columnas JSON**: Después de la normalización, eliminé las columnas JSON del dataframe original.
5. **Análisis del DataFrame Final**: Utilicé la función `info()` para examinar el dataframe final y comprobar la cantidad de entradas, columnas y el tipo de datos de cada una.
6. **Búsqueda de Valores Únicos y Vacíos**: Con `unique()`, identifiqué los valores únicos y vacíos. En la columna "Charges.total", encontré 11 valores en blanco, que fueron reemplazados por **0** asumiendo que eran nuevos clientes sin pagos pendientes.
7. **Cambio de Tipo de Dato**: Cambié el tipo de la columna "Charges.Total" de "object" a "float" utilizando la función `astype(np.float)` de **Numpy**.
8. **Transformación a Minúsculas**: Transformé todas las columnas de tipo string a minúsculas.
9. **Reemplazo de "Yes" y "No"**: Reemplacé los valores "yes" y "no" por "1" y "0", respectivamente.
10. **Cálculo de Cuentas Diarias**: Calculé la columna "Cuentas diarias" dividiendo la columna "Charges.Monthly" entre 30, el número promedio de días por mes.

## **Análisis Exploratorio de Datos 📈 📉 🔎**

### **Proporción de Clientes que Permanecen y se Han Dado de Baja**

* **Total de Clientes**: 7,267
* **Clientes que permanecen**: 5,398 (74.3%)
* **Clientes dados de baja**: 1,869 (25.7%)

### **Distribución de la Evasión por Género, Tipo de Contrato y Medio de Pago**

#### **Evasión según Género**

* **Mujeres**: 50.2% de los evasores (1,869)
* **Hombres**: 49.7% de los evasores (1,869)
* **Conclusión**: La diferencia es mínima (0.5%), por lo que el género no parece ser un factor determinante en la evasión de clientes.

#### **Evasión según Medio de Pago**

Los medios de pago utilizados en el dataframe son:

* **Bank Transfer (automatic)**: 13.8%
* **Credit Card (automatic)**: 12.4%
* **Electronic Check**: 57.3%
* **Mailed Check**: 16.4%

**Conclusión**: El medio de pago **"Electronic Check"** tiene la mayor tasa de evasión. TelecomX debería centrarse en reducir la evasión en este método, ofreciendo incentivos para que los nuevos clientes opten por métodos con menor tasa de evasión.

#### **Evasión según Tipo de Contrato**

* **Two Year**: 2.56% de evasión
* **Month to Month**: 88.55% de evasión
* **One Year**: 8.88% de evasión

**Conclusión**: Los contratos **"Month to Month"** son los que presentan la mayor tasa de evasión. Se recomienda ofrecer incentivos para planes más largos, como descuentos por fidelidad.

### **Distribución del Tiempo de Contrato**

Los clientes que cancelaron el servicio lo hicieron principalmente en los primeros meses de contrato, lo que sugiere que los primeros meses son un período crítico para la retención de clientes.

### **Distribución del Gasto Total**

La mayoría de los clientes, tanto los que cancelaron como los que permanecen, tienen un bajo gasto. Sin embargo, los usuarios que se quedan son significativamente más numerosos en casi todos los niveles de gasto, lo que es un indicio positivo para la empresa.

## **Conclusiones e Insights Clave 📊**

1. **Alta Tasa de Evasión General**: Un **25.7%** de los clientes se dieron de baja, lo que resalta la necesidad urgente de estrategias de retención.
2. **El Género No es un Factor Determinante**: La diferencia en la evasión entre hombres y mujeres es mínima.
3. **"Electronic Check" es el Principal Factor de Evasión**: Este medio de pago representa el **57.3%** de los evasores.
4. **"Month to Month" es el Tipo de Contrato con Mayor Evasión**: Los contratos mensuales tienen una tasa de evasión muy alta (88.55%).
5. **Evasión Temprana**: La mayoría de las cancelaciones ocurren en los primeros meses de contrato.
6. **Concentración de Evasión en Bajos Niveles de Gasto**: Los clientes con menor gasto son más propensos a cancelar el servicio.

## **Recomendaciones Estratégicas 💡**

### **1. Priorizar Contratos a Largo Plazo**

* **Acción**: Incentivar la contratación de planes a largo plazo (1-2 años).
* **Estrategia**: Ofrecer **descuentos de fidelidad** y beneficios exclusivos para contratos largos.

### **2. Promover Medios de Pago con Baja Tasa de Evasión**

* **Acción**: Desincentivar el uso de "Electronic Check".
* **Estrategia**: Implementar campañas con **descuentos** y **beneficios** para clientes que elijan medios de pago automáticos.

### **3. Fortalecer la Retención Temprana de Clientes**

* **Acción**: Implementar programas de bienvenida y seguimiento durante los primeros meses.
* **Estrategia**: Ofrecer una excelente experiencia de instalación y comunicación proactiva con los clientes.

### **4. Investigar el Comportamiento de Gasto y Percepción de Valor**

* **Acción**: Realizar estudios sobre la cancelación de clientes con bajo gasto.
* **Estrategia**: Implementar **encuestas de salida** para conocer las razones de la cancelación y revisar los procesos de soporte post-venta.

