# proyecto_10_optimizacion
Optimización de Ingresos en Tienda Online | Priorización de Hipótesis | Análisis de Test A/B | ICE | RICE | Diferencia Relativa | Tasa Conversión Acumulada

# OPTIMIZACIÓN DE INGRESOS EN TIENDA ONLINE: PRIORIZACIÓN DE HIPÓTESIS Y ANÁLISIS DE TEST A/B

## RESUMEN DEL PROYECTO
El objetivo es mejorar los ingresos de una tienda online mediante un enfoque analítico basado en datos. Se divide en dos fases:
1. Marcos de priorización (ICE y RICE) a una serie de hipótesis de crecimiento para determinar cuáles tienen el mayor potencial y deben ser probadas.
2. Análisis exhaustivo de los resultados de un Test A/B ya ejecutado, examinando métricas acumuladas y la significancia estadística de las diferencias entre los grupos de control y tratamiento, tanto con datos brutos como filtrados.

## OBJETIVO
Proporcionar recomendaciones basadas en datos para optimizar los ingresos mediante:
1. Priorización efectiva de hipótesis de crecimiento
2. Análisis riguroso de un test A/B para determinar su efectividad

## METODOLOGÍA DE ANÁLISIS

### 1. DESCRIPCIÓN DE LOS DATOS
**Datasets utilizados:**
- `hypotheses_us.csv`: 9 hipótesis con métricas de Reach, Impact, Confidence y Effort
- `orders_us.csv`: Datos de transacciones (ID pedido, ID usuario, fecha, ingresos, grupo A/B)
- `visits_us.csv`: Datos de visitas diarias por grupo A/B

### 2. PREPROCESAMIENTO DE DATOS
#### 2.1 Limpieza y transformación
- Conversión de formatos de fecha
- Estandarización de nombres de columnas
- Verificación y manejo de valores nulos
- Identificación y exclusión de usuarios en ambos grupos (58 usuarios)

#### 2.2 Filtrado de valores atípicos
- Usuarios con >4 pedidos (percentil 99)
- Pedidos > $900.90 (percentil 99)
- Total usuarios filtrados: 21 (82 pedidos)

### 3. PRUEBA DE HIPÓTESIS
#### 3.1 Priorización con ICE y RICE

**Framework ICE (Impact, Confidence, Effort):**
| Hipótesis | ICE |
|-----------|-----|
| Launch a promotion that gives users discounts | 16.20 |
| Add two new channels for attracting traffic | 13.33 |
| Add a subscription form to all the main pages | 11.20 |

**Framework RICE (Reach, Impact, Confidence, Effort):**
| Hipótesis |RICE|
|-----------|----|
| Add a subscription form to all the main pages |112.0 |
| Add product recommendation blocks to the store |56.0 |
| Add two new channels for attracting traffic |40.0 |


#### 3.2 Análisis Test A/B
**Métricas clave:**
- **Conversión:** 
  - Diferencia relativa: +13.8% (datos crudos), +13.1% (datos filtrados)
  - p-value: 0.023 (crudo), 0.013 (filtrado) → **Significativo**
  
- **Tamaño promedio pedido:**
  - Diferencia relativa: +25.2% (crudo), -1.4% (filtrado)
  - p-value: 0.692 (crudo), 0.910 (filtrado) → **No significativo**

## CONCLUSIONES PRINCIPALES
1. **Priorización de hipótesis:**
   - La hipótesis "Add a subscription form..." es la mejor candidata para implementar (RICE=112)
   - Los frameworks ICE y RICE muestran diferencias importantes al considerar el alcance (Reach)

2. **Resultados Test A/B:**
   - El Grupo B muestra una mejora **estadísticamente significativa** en la tasa de conversión (+13%)
   - **No hay diferencia significativa** en el tamaño promedio de pedido
   - Los valores atípicos distorsionaban inicialmente las métricas de ingresos

3. **Recomendación final:**
   - Implementar la versión B (nueva versión) por su impacto positivo en conversión
   - Monitorear métricas post-implementación
   - Enfocar futuras optimizaciones en aumentar el valor promedio del carrito

## TECNOLOGÍAS UTILIZADAS
- **Python** (Lenguaje principal)
- **Pandas** (Manipulación de datos)
- **NumPy** (Cálculos numéricos)
- **Matplotlib/Seaborn** (Visualización)
- **SciPy** (Pruebas estadísticas)
