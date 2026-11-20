# Proyecto RappiPlus
**Diagnóstico estratégico integral para RappiPlus**  
**Objetivo**: Evaluar el desempeño del servicio RappiPlus para apoyar decisiones de negocio basadas en datos.  
**Herramientas utilizadas:** SQL, Pandas, Python, A/B Testing & Power BI  
**Datasets del negocio:**  
rappiplus_orders_raw.csv → información de pedidos, precios, descuentos y revenue  
rappiplus_catalog.csv → costos de productos, categorías y proveedores  
rappiplus_marketing_spend.csv → inversión en marketing por canal y país  
events / users / user_activity (SQL) → comportamiento del usuario dentro de la plataforma  
experiment_checkout_ui.csv → resultados de un experimento A/B en el checkout  
**Paso 1:** Cargar y validar la calidad de los datos  
Se revisan los 3 datasets:  
Validar y convertir fechas al formato correcto ✅  
Revisar variables numéricas (sin negativos o ceros inválidos) ✅  
Verificar consistencia de montos ✅  
Eliminar duplicados ✅  
Revisar variables categóricas ✅  
**Paso 2:** Analizar si el negocio es rentable  
💰 **Resultados Financieros y de Ventas**  
📊 **Rentabilidad del negocio**  
Ingreso Total (Revenue): $9,643,566  
Costo Total: $3,848,651  
Utilidad (Profit) Bruta: $5,794,915  
Inversión en Marketing: $2,871,844  
Utilidad (Profit) Neta: $2,923,071  
Margen Neto de Ganancia: 30.3%  
**Se concluye que el negocio de RappiPlus es rentable con un margen del 30.3% lo que para una plataforma de este tipo está en los límites aceptables** ✅  
📈 **Comportamiento de ventas** 
Ticket promedio por orden: $386.02  
Cantidad promedio de productos por orden: 1.54  
Producto más vendido: Sneakers-Urban-42 (6,664 unidades)  
Gasto en marketing por canal:  
social $918,043.21  
organic $913,533.01  
paid_search $863,088.21  
**Paso 3:** Entender dónde se pierden los usuarios (funnel de conversión)  
📊 **Construcción del funnel**  
usuarios únicos que llegan a cada etapa del funnel:  
first_visit: 7,796 (Primera Visita)  
select_item: 7,582 (Seleccionar Item)  
add_to_cart: 7,634 (Agregar al Carro)  
begin_checkout: 7,208 (Empezar Checkout)  
add_payment_info: 6,250 (Agregar Información de Pago)  
purchase: 6,240 (Compra)  
📉 **Análisis de conversión**  
Se calcula la tasa de conversión entre cada paso del funnel  
select_item: 97.26%  
add_to_cart: 100.69%  
begin_checkout: 94.42%  
add_payment_info: 86.71%  
purchase: 99.84%  
**La etapa donde se pierde la mayor cantidad de usuarios es entre begin_checkout y add_payment_info y es del 13.29%, se tendría que revisar si hay algo al agregar la información de pago que haga que el usuario abandone**  
**La tasa de conversión final es del 80.04% la cual es muy alta para este tipo de plataformas. La propuesta de valor de la plataforma logra retener e impulsar la intención de compra de manera eficiente**  
**Paso 4:** Evaluar si los usuarios regresan (retención por cohortes)  
**El porcentaje de retención a través de las 3 primeras semanas se mantiene en un rango muy estable e inusualmente alto entre un 37% y un 47%. Eso significa que los usuarios regresan de forma consistente semana a semana.**  
**A excepción de la semana de inicio, el flujo de captación de usuarios se mantiene a lo largo de las semanas entre 350 a 400 usuarios.
El cohorte con mejor comportamiento a lo largo del tiempo fue el de la semana 14 con una retención promedio de arriba del 45% seguido por las semanas 4, 5 y 15.**  
**Paso 5:** Validar si los cambios generan impacto (test estadístico)  
Después de aplicar la prueba estadística z, obtuvimos los siguientes resultados:  
Estadístico z: -0.8133  
Valor p: 0.4161  
**Por lo tanto no se rechaza la hipótesis nula: NO hay evidencia suficiente de una diferencia en la tasa de conversión de ambas variantes**  
Así mismo mostramos las tasas de conversión:  
Tasa de conversión Control: 15.69%  
Tasa de conversión Tratamiento: 16.29%  
Diferencia en tasas de conversión: 0.60%  
**Por lo tanto el cambio implementado en el tratamiento no generó una mejora estadísticamente relevante, se tendrá que revisar y hacer mejoras**  
**Paso 6:** Comunicar los resultados (Dashboard en Power BI)  
![Dashboard RappiPlus - Página1](Dashboard_Power_BI_RappiPlus_Ernesto_Parra_page-0001)
![Dashboard RappiPlus - Página2]  (Dashboard_Power_BI_RappiPlus_Ernesto_Parra_page-0002)  
