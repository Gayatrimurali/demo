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

8. Power BI comenzará a crear de forma automática el informe. Observe que hay una opción para seleccionar previamente los datos si así lo queremos. Una vez que el informe esté listo, aparecerá un cuadro de diálogo en la parte superior derecha de la pantalla. Seleccione **Ver informe ahora**.

   >**Punto de control**: tendrá un informe similar a la captura de pantalla siguiente. Hay algunos KPI y algunos objetos visuales de tendencias. Este es un buen comienzo si está analizando un nuevo modelo y necesita un impulso. 

   >**Nota**: Observe que en el menú superior tiene la opción de editar el informe o ver algunos de los datos como tablas. No dude en explorar estas opciones.

9. Una vez que esté listo, **contraiga** todas las tablas en la sección **Datos** de la derecha. Observe que tenemos cinco tablas nuevas que no forman parte del modelo que creamos. Son tablas predeterminadas agregadas para ayudar a analizar el rendimiento. Las eliminaremos de la vista del informe en breve. 

10. Guardemos este informe. En el menú superior, seleccione **Guardar**. 

11. Se abre el cuadro de diálogo Guardar el informe. Nombre el informe como **rpt_Sales_Auto_Report**  

    >**Nota**: Estamos anteponiendo rpt al nombre del informe, que es la abreviatura de informe (en inglés). 

12. Asegúrese de que el informe esté guardado en **<your workspace name>**. 

13. Seleccione **Guardar**.

### Tarea 2: Ocultar tablas predeterminadas (métricas) 

Creemos un informe como el que tenemos en Power BI Desktop. Lo vamos a hacer desde un lienzo en blanco. Antes de comenzar a crear un informe, eliminemos las tablas predeterminadas (captura de pantalla anterior) de la vista del informe. Esto se hace en la sección de modelado del lakehouse. 

1. En la parte inferior del panel de navegación de la izquierda, seleccione **el icono de Power BI**. Se abre el cuadro de diálogo de Fabric. 

2. Seleccione **Data Engineering**. Se le dirigirá a la página principal de Data Engineering.

3. Desplácese hacia abajo hasta la sección **Acceso rápido**. 

4. Seleccione **lh_FAIAD -> Punto de conexión de análisis SQL**. Estaremos en la vista Datos del lakehouse. 

5. Desde la **parte inferior del panel izquierdo**, seleccione **Modelo** para navegar a la vista Modelo. 

Observe que en el lienzo de diseño encontrará las tablas predeterminadas. (Es posible que tenga que desplazarse hacia la derecha o hacia abajo para verlos).

6. Haga clic derecho en la tabla **long_running_queries** y seleccione **Ocultar en la vista de Informes**.

7. De manera similar, seleccione la opción **Ocultar en la vista de Informes** para las siguientes tablas: 

    - fabric_query_starting 
    - fabric_query_completed 
    - exec_requests_history 
    - frequently_run_queries

### Tarea 3: Configurar el fondo para un nuevo informe 

1. Podemos comenzar a crear un nuevo informe desde la vista del modelo. En el menú superior, seleccione **Inicio -> Nuevo informe**. Se le dirigirá al lienzo del informe de Power BI en una nueva ventana o pestaña en su explorador.

2. Si aún no lo ha abierto, abra **FAIAD.pbix**, que se encuentra en la carpeta **Report** en el **Escritorio** de su entorno de laboratorio.  

Vamos a utilizar este informe como referencia. Comenzaremos agregando el fondo del lienzo. Crearemos el encabezado del informe, agregaremos un par de KPI y crearemos el gráfico de líneas de Ventas a lo largo del tiempo. Por razones de tiempo y sabiendo que tiene experiencia en la creación de objetos visuales en Power BI Desktop, no crearemos todos los objetos visuales

3. Vuelva al **lienzo de Power BI** en su explorador. 

4. Seleccione el **icono** de **la página Formato** en el panel de Visualizaciones. 

5. Expanda la **sección Fondo del lienzo**. 

6. Seleccione la opción **Examinar** de la opción **Imagen**. Se abre el cuadro de diálogo Explorador de archivos. 

7. Navegue hasta la carpeta **Report** en el **Escritorio** de su entorno de laboratorio.  

8. Seleccione **Summary Background.png**. 

9. Establezca el menú desplegable **Ajuste de imagen** en **Ajustar**. 

10. Establezca la Transparencia en **0 %**.

### Tarea 4: Agregar un encabezado al informe

1. Agreguemos el encabezado en el margen superior. En el **menú**, seleccione **Cuadro de texto**. 

2. Introduzca **Fabrikam Company** como primera línea en el cuadro de texto. 

3. Introduzca **Sales Report** como segunda línea en el cuadro de texto. 

4. Resalte **Fabrikam Company** y establezca la **Fuente** en **Segoe UI** y el **tamaño de fuente** a **18**, **negrita**. 

5. Resalte **Informe de ventas** y establezca la **Fuente** en **Segoe UI** y el **tamaño de fuente** a **14**, **negrita**. 

6. Con el **cuadro de texto seleccionado**, en el panel Formato de la derecha, **expanda la sección Efectos**. 

7. Utilice el control deslizante **Fondo** para configurarlo en **Desactivado**. 

8. Cambie el tamaño del cuadro de texto **para que quepa en el margen superior**.

### Tarea 5: Agregar KPI al informe 

1. Agreguemos KPI de ventas. Seleccione el **espacio en blanco** en el lienzo para quitar el foco del cuadro de texto. 

2. En la **sección Visualizaciones**, seleccione el **objeto visual Tarjeta de varias filas**. 

3. En la sección Datos, expanda la **tabla Sales**. 

4. Seleccione **la medida Sales**.

5. Con **el objeto visual de tarjeta de varias filas seleccionado**, seleccione el **icono Dar formato a objeto visual** en la sección Visualizaciones. 

6. Expanda la sección **Etiquetas de categorías.** 

7. Aumente el **tamaño de fuente** a **14**. 

8. Seleccione el **menú desplegable Color**. Se abre el cuadro de diálogo Paleta de colores. 

9. Establezca el valor Hex en **#004753**.

10. Expanda la sección **Tarjetas**. 

11. Utilice el control deslizante **Barra de énfasis** para configurarlo en **Desactivado**.

12. Seleccione **General** en el panel de Visualizaciones. 

13. Expanda la **sección Efectos**. 

14. Utilice el control deslizante **Fondo** para configurarlo en **Desactivado**. 

15. Cambie el tamaño del **objeto visual** y muévalo al **cuadro izquierdo como se muestra en la captura de pantalla**.

16. Vamos a agregar otro KPI. Seleccione la **Tarjeta de varias filas de Sales** que acabamos de crear. **Copie** el objeto visual mediante la selección de **Ctrl+C** desde tu teclado. 

17. **Pegue** el objeto visual mediante la selección de **Ctrl+V** desde tu teclado. Observe que el objeto visual se pega en el lienzo. 

18. Con el **nuevo objeto visual resaltado**, en la sección **Visualizaciones -> Crear objeto visual -> Campos**, elimine la medida **Sales**. 

19. Desde la sección **Datos**, expanda la tabla **Sales** y seleccione la medida **Units**. 

20. Cambie el tamaño del **objeto visual** y **colóquelo en el cuadro debajo del objeto visual Sales**.

### Tarea 6: Agregar un gráfico de líneas al informe 

Creemos un gráfico de líneas para visualizar las ventas a lo largo del tiempo por empresa revendedora. 

1. Seleccione el **espacio en blanco** en el lienzo para quitar el foco del objeto visual de tarjeta de varias filas. 

2. En la **sección Visualizaciones**, seleccione **Gráfico de líneas**. 

3. En la **sección Datos**, expanda la tabla **Date**. 

4. Seleccione el campo **Year**. Tenga en cuenta que Year se suma de forma predeterminada y se agrega al eje Y. Rectifiquemos esto.

### Tarea 7: Configurar la columna Year en la tabla Date 

1. Navegue a la pestaña del explorador con la **vista del modelo del lakehouse**. 

2. En el panel izquierdo del explorador, expanda **lhFAIAD -> Schemas -> dbo -> Tables -> Date**. 

3. Seleccione la columna **Year**. 

4. En el panel **Propiedades** de la derecha, expanda la sección **Avanzado**. 

5. En el menú desplegable **Resumir por**, seleccione **Ninguno**.

6. Vuelva a la pestaña del explorador con el **lienzo de Power BI**. 

7. En el menú superior, seleccione **Actualizar**. Observe ahora que Year no es un campo de suma.  

8. Con el **objeto visual Gráfico de líneas seleccionado**, **elimine la Sum of Year** del eje Y. 

9. Seleccione el campo **Year** y se agregará al **eje X**. 

10. Expanda la tabla **Sales** y seleccione la **medida Sales**.

### Tarea 8: Configurar la columna Short_Month_Name en la tabla Date 

1. Agreguemos Mes a este gráfico. Desde la tabla Date, arrastre el campo **Short_Month_Name** debajo de **Year** en el **eje X**. Observe que el objeto visual está ordenado por Sales. Ordenémoslo por Short_Month_Name. 

2. Haga clic en los **puntos suspensivos (…)** en la esquina superior derecha del objeto visual. 

3. Seleccione **Ordenar eje -> Year Short_Month_Name**. 

4. Haga clic en los **puntos suspensivos (…)** en la esquina superior derecha del objeto visual. 

5. Seleccione **Ordenar eje -> Orden ascendente**. 

   >**Nota:** Los meses están ordenados alfabéticamente. Vamos a arreglarlo. 

6. Navegue a la pestaña del explorador con la **vista del modelo del lakehouse**. 

7. En el panel izquierdo del explorador, expanda **lhFAIAD -> Schemes -> dbo -> Tables -> Date**. 

8. Seleccione la columna **Short_Month_Name**. 

9. En el panel **Propiedades** de la derecha, expanda la sección **Avanzado**. 

10. En el menú desplegable **Ordenar por columna** seleccione **Month**.

11. Vuelva a la pestaña del explorador con el **lienzo de Power BI**. 

12. En el menú superior, seleccione **Actualizar**. Observe que ahora los meses están ordenados correctamente.

### Tarea 9: Aplicar formato al gráfico de líneas 

Observe lo fácil que es actualizar el modelo semántico mientras se crean los informes. Esto proporciona una interacción fluida como Power BI Desktop. 

1. Con el **objeto visual Gráfico de líneas seleccionado**, en la **sección Datos**, expanda la tabla **Reseller**. 

2. Arrastre **Reseller -> Reseller Company** a la sección **Leyenda**.

3. Con el **objeto visual Gráfico de líneas seleccionado**, en la sección **Visualizaciones**, seleccione **icono Formato visual -> General**. 

4. Expanda la sección **Título**. 

5. Establezca el texto **Título** en **Ventas a lo largo del tiempo**. 

6. Expanda la sección **Efectos**. 

7. Utilice el control deslizante **Fondo** para configurarlo en **Desactivado**.

8. En la sección **Visualizaciones**, seleccione el **icono Formato de objeto visual -> Objeto visual**. 

9. Expanda la sección **Eje X**. 

10. Utilice el control deslizante Título para configurarlo en **Desactivado**. 

11. Expanda la sección **Líneas**. 

12. Expanda la sección **Colores**. 

13. Establezca el color de **Wingtip Toys** en **#004753**. 

14. Establezca el color de **Tailspin Toys** en **#F17925**. 

15. Cambie el tamaño del **objeto visual** y muévalo al **cuadro superior derecho como se muestra en la captura de pantalla**. 

16. Desplácese hacia la derecha en el objeto visual y **observe que tenemos datos hasta abril de 2023**.

17. Guardemos el informe: desde el menú, seleccione **Archivo -> Guardar**. 

18. Se abre el cuadro de diálogo Guardar el informe. Nombre el informe como **rpt_Sales_Report**  

    >**Nota**: Estamos anteponiendo rpt al nombre del informe, que es la abreviatura de informe (en inglés). 

19. Asegúrese de que el informe esté guardado en **<your workspace name>**. 

20. Seleccione **Guardar**.

Como se mencionó anteriormente, no crearemos todos los objetos visuales en esta práctica de laboratorio. Siéntase libre de crear más objetos visuales si lo desea.  

### Tarea 10: Agregar nuevos datos para simular el modo Direct Lake 

Normalmente, en el modo Import, una vez que se actualizan los datos en el origen, necesitamos actualizar el modelo de Power BI y después se actualizan los datos en el informe. Con el modo de Direct Query, una vez que los datos se actualizan en el origen, están disponibles en el informe de Power BI. Sin embargo, el modo de Direct Query suele ser lento. Para resolver este problema, Microsoft Fabric presenta el modo Direct Lake. Direct Lake es una ruta rápida para cargar los datos del lago directamente en el motor de Power BI listos para su análisis. Exploremos más. 

En un escenario real, los datos se actualizan en el origen. Como estamos en un entorno de entrenamiento, lo simularemos mediante la conexión a un archivo Parquet con datos de mayo de 2023.  

1. Navegue a la pestaña del explorador con la **vista del modelo del lakehouse**. 

2. Seleccione **<your workspace name>** en el panel izquierdo. 

3. Seleccione df_Sales_ADFS para que podamos editar el flujo de datos al agregar el nuevo archivo Parquet. 



