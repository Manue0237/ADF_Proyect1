# Desafío de Datos en Azure

## Descripción General
Este repositorio contiene la solución para el Desafío de Datos en Azure. El objetivo es construir una solución de datos escalable y eficiente utilizando los Servicios de Datos de Azure para manejar grandes volúmenes de datos en un entorno de producción.

## Pasos del Desafío

1. **Configurar el Entorno**:
   - Copiar `CustomerData.csv` a `C:\Kaits\Inbox\`.
   - Instalar el gateway para importar `CustomerData.csv` al contenedor en la nube de Azure.
   - Crear carpetas en Azure Data Lake Gen2:
     - `Kaits\Inbox`
     - `Kaits\Processed`
   - Crear una base de datos llamada `Kaits` en Azure SQL Database.
   - Ejecutar scripts para crear las tablas `DimCustomers` y `DimGeography`:
     - `Tables_SQL2012.sql` o
     - `Tables_SQL2014.sql`
   - Asegurarse de que `DimGeography` tenga 655 registros y `DimCustomers` esté vacía.

2. **Procesamiento de Datos**:
   - Cargar `CustomerData.csv` en la tabla `DimCustomers` utilizando un pipeline.
   - Mapear `City` y `CountryRegionCode` al `GeographyKey` en `DimGeography`.
   - Implementar lógica SCD1 en el pipeline.
   - Mover el archivo procesado a `Kaits\Processed`.

## Criterios de Validación
1. La primera ejecución del pipeline debe insertar en la tabla `DimCustomers` la misma cantidad de registros que en el archivo.
2. La segunda ejecución con el mismo archivo no debe insertar ningún registro nuevo si no hubo cambios.
3. Modificar el archivo y ejecutar el pipeline debe actualizar el registro modificado.
4. Asegurarse de que el archivo se mueva a la carpeta `Processed` después de cada ejecución.

## Puntos Adicionales
- Implementar la solución utilizando servicios de datos adicionales de Azure.
