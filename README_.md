# 🍔 TPI Python: Pipeline ETL de Food Delivery (EE.UU.)

Proyecto final del curso **Python para Análisis de Datos (ETL)**.

Pipeline ETL para una startup de delivery que quiere expandirse en Estados Unidos: se leen los datos crudos de restaurantes y menús, se limpian, se cargan en una base SQLite y se responden preguntas del CEO con SQL y gráficos.

## Datos
- `restaurants.csv`: catálogo de restaurantes (~63 mil filas).
- `restaurant_menus_parte_1.csv` ... `restaurant_menus_parte_10.csv`: platos y precios de cada restaurante.

## Qué hace el notebook
1. **Extract:** lee los CSV (los 10 archivos de menús se unen en un solo DataFrame) y revisa dimensiones, tipos y nulos.
2. **Transform:**
   - convierte los símbolos `$` en categorías (Económico, Moderadamente caro, Caro, Muy caro)
   - separa la dirección en calle, ciudad y estado/zip
   - elimina restaurantes sin score y platos sin precio
   - se queda con restaurantes de más de 100 calificaciones y los cruza con los menús
3. **Load:** guarda la tabla final `master_food_data` en `delivery_insights.db` (SQLite).
4. **BI:** 4 consultas SQL con su gráfico y conclusión para el CEO.

## Preguntas que responde
1. ¿Qué 5 ciudades tienen más restaurantes consolidados?
2. ¿Cómo se distribuyen los restaurantes por rango de precio?
3. ¿Cuál es el precio promedio de un plato en las 3 ciudades principales?
4. ¿Un restaurante más caro garantiza mejor calidad?

## Cómo ejecutarlo
1. Abrir `Proyecto_ETL_Delivery.ipynb` en Google Colab.
2. Crear una carpeta `data` y subir ahí `restaurants.csv` y los 10 archivos de menús.
3. Ejecutar todas las celdas.

## Tecnologías
Python, Pandas, SQLAlchemy, SQLite, Matplotlib, Seaborn.

## Autor
Edy Enrique Nina Huillca
