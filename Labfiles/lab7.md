# ​​Contenido 

## Presentación  

## Power BI 

- Tarea 1: Crear un informe de forma automática
- Tarea 2: Ocultar tablas predeterminadas (métricas)
- Tarea 3: Configurar el fondo para un nuevo informe
- Tarea 4: Agregar un encabezado al informe
- Tarea 5: Agregar KPI al informe
- Tarea 6: Agregar un gráfico de líneas al informe
- Tarea 7: Configurar la columna Year en la tabla Date
- Tarea 8: Configurar la columna Short_Month_Name en la tabla Date
- Tarea 9: Aplicar formato al gráfico de líneas
- Tarea 10: Agregar nuevos datos para simular el modo Direct Lake

## Limpieza del entorno de laboratorio 

## Referencias 

## Presentación  

Absorbimos datos de diferentes orígenes de datos a un lakehouse, conocimos los lakehouse, creamos un modelo de datos y establecimos una programación de actualización para los orígenes de datos. Ahora vamos a crear un informe. 

Al final de este laboratorio, habrá aprendido:  

- Cómo crear un informe de forma automática
- Cómo crear un informe a partir de un lienzo en blanco
- Cómo usar el modo Direct Lake, que da como resultado una actualización automática de los datos

## Power BI 

### Tarea 1: Crear un informe de forma automática 

Comencemos con la opción de creación automática de informes. Y, más adelante en el laboratorio, volveremos a crear el informe que tenemos en Power BI. 

1. Volvamos **al área de trabajo de Fabric** que creó en el laboratorio anterior. 

2. Seguramente esté en la página principal de Data Factory. En la parte inferior del panel de navegación de la izquierda, seleccione el **icono de Data Factory**. 

3. Se abre el cuadro de diálogo de experiencia de Fabric. Seleccione **Power BI**. Se le llevará al **Inicio de Power BI**.

4. Seleccione **Nuevo informe** en el menú superior.

5. Se le dirigirá a la **pantalla de creación de su primer informe**. Habrá opciones para introducir datos manualmente y crear un informe o elegir un modelo semántico publicado. Hemos creado un modelo semántico en los laboratorios anteriores. Usemos ese. Seleccione la opción **Selección de un modelo semántico publicado**.

6. Se abre la página Elija un conjunto de datos para usar en su informe. Observe que tenemos cuatro opciones. **Seleccione lh_FAIAD**: 

    - **lh_FAIAD**: este es el lakehouse con el conjunto de datos que creamos y que queremos usar para el informe. 

    - **Units by Supplier**: este es el conjunto de datos que creamos con T-SQL. 

    - **DataflowsStagingWarehouse**: este es el almacén de almacenamiento provisional que se crea de forma predeterminada, ya que no lo utilizamos porque no preparamos datos. 

    - **DataflowsStagingLakehouse**: este es el lakehouse provisional que se crea de forma predeterminada, ya que no lo utilizamos porque no preparamos datos. 

7. Haga clic en la flecha **junto al botón Crear informe de forma automática**. Observe que hay dos opciones: Crear informe de forma automática y Crear un informe en blanco. Probemos la creación automática: seleccione **Crear informe de forma automática**. 


