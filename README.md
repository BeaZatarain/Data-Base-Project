# Data-Base-Project

![Portada](https://github.com/BeaZatarain/Data-Base-Project/blob/main/images/encabezadovideoclub.png)

## Descripción general del proyecto

Este proyecto consiste en crear una base de datos en Mysql, utilizanto Mysql Workbench y Python. 

Concretamente, el objetivo ficticio de este proyecto es que un cliente, dueño de dos videoclubs que ha cerrado, quiere abrir un tercero y acude a nosotros para construir una base de datos desde cero. Para ello, nos entrega 7 CSVs con información de sus antiguos negocios.

A continuación se procederá a explicar el procedimiento que se ha realizado para completar este proyecto.

## Limpieza y Exploración de datos 

Para la limpieza y la exploración de los datos, hemos utilizado Python y concretamente Pandas para llevar a cabo nuestro objetivo. 

Con ello, este proceso ha consistido básicament en: 

1. Explorar que información contiene cada CSV entregado por el cliente de cara a, posteriormente, facilitarnos las futuras relaciones que se crearán en el momento de crear la base de datos. 

2. Limpieza de información que no aportaba valor a la base de datos (columnas constantes, duplicados, nulos...)

Finalmente, tras todo este proceso, hemos importado los CSVs a Mysql para crear la base de datos. Cabe remarcar que, tras este proceso:

 - El CSV de old_HDD, ha sido dividido en dos "tablas puente". Por un lado, old_HDD1.csv con el fin de ser tabla intermedia entre films y actors y por otro, old_HDD2.csv, que relacionado con la tabla de films, nos proporcionará la informaición necesaria para consultar las categorías de todas las películas. 

 - El CSV de category, no ha sido importado ya que tras el proceso de limpieza en Python, la información que contenía se ha incluido en old_HDD2.csv como tabla puente de conexión.
 
 En definitiva, los CSVs que se han importado son los siguientes:
 
 ![imports](https://github.com/BeaZatarain/Data-Base-Project/blob/main/images/csvsimport.png)
 

## Creación de la Base de Datos 'Vidieoclub'


Una vez finalizado el proceso de exploración y limpieza de los datos aportados por el cliente, se ha llevado a cabo un proceso de análisis para establecer las relaciones entre las tablas de la nueva base de datos. 

También, se ha analizado cuidadosamente, el tipo de dato que contiene cada columna de las identidades de la base de datos para evitar errores a la hora de la creación. 

Con ello, el resultado final, se puede apreciar en la siguiente imagen:

 ![Relaciones](https://github.com/BeaZatarain/Data-Base-Project/blob/main/images/Relacion_BD.png)




Tal y como se puede observar, la identidad o tabla "rental" ha sido la única que no ha sido relacionada con el resto de identidades. 

Esto se debe a que se tratar de un negocio ficticio que no ha comenzado su actividad en el mercado aún. Es por ello, que se ha tomado la decisión de dejar la tabla como histórico de su actividad a modo de consulta. 

Por tanto, teóricamente, cuando el negocio comenzase su actividad y tuviese más claro sus procesos internos, se crearía una tabla nueva en función de sus necesidades y relacionaría mediante una query con la tabla de inventory (a través del inventory_id).





