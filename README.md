# tc-sql-raulmolina

Este proyecto tiene dos partes:
* Parte 1 - SQL MURDER MYSTERY: Consiste en encontrar al asesino a través de una serie de tablas siguiendo lo indicado en la web https://mystery.knightlab.com/
  * **IMPORTANTE: Cuando realicé la tarea la web estaba caida, por tanto lo hice todo en vs code sin apoyo de la web. No obstante entiendo que el resultado es el mismo**

* Parte 2: Construcción de una estructura de datos en una BBDD real y carga de datos y lanzamiento de querys desde Python.

  * **IMPORTANTE: En el curso se propuso usar la BBDD BigQuery de google, pero se dejó libertad para usar otra BBDD y generar los scripts en otro formato que no fuera el de python. Por este motivo se ha utilizado Oracle Express 21 c, para evitar generar gasto en google cloud y con el que estoy más comodo. Para más detalle ver apartado correspondiente**

## Estructura del repositorio

Esta es la estructura completa del repositorio del Team Challenge (incluye las dos partes):

```
tc-sql-raulmolina/
├── parte_1_sql_murder_mystery/
│   └── investigacion.ipynb
├── parte_2_modelo_oracleXE/
│   ├── docs/
│   │   ├── er_diagram.png
│   │   └── er_diagram.mermaid
│   └── src/
│       ├── 00_DROPS.sql
│       ├── 01_CREATES.sql
│       ├── 02_generate_data.ipynb
│       └── 03_queries_verification.ipynb
├── .env.example
├── .gitignore
├── README.md
└── requirements.txt
```

### Parte 2: Modelo de datos bajo Oracle XE - Información ampliada

* BBDD utilizada: **Oracle XE 21 c**
* IDE de ejecucion scripts .sql: **SQL*Developer**
* Para descargar Oracle XE: https://www.oracle.com/es/database/technologies/xe-downloads.html
* Para descargar SQL*DEVELOPER: https://www.oracle.com/es/database/sqldeveloper/
* Creación de BBDD. Ejemplo:
  * Conectar con usuario SYS as SYSDBA y SID XE.
  * Ejecutar script de creación de usuario:

    ```
    -- 1. Permite crear usuarios sin el prefijo C## bajo el SID XE como sysdba.
    ALTER SESSION SET "_ORACLE_SCRIPT" = true;

    -- 2. Crea tu usuario
    CREATE USER MySchema IDENTIFIED BY MySchemaPass;

    -- 3. Dale los permisos necesarios para trabajar
    GRANT CONNECT, RESOURCE, DBA TO MySchema;
    ALTER USER TC03SQLBRIDGE QUOTA UNLIMITED ON USERS;
    ```
* Ejecución de ficheros .sql: Se debe ejecutar en SQL*Developer previa conexión con el usurio/schema de BBDD creado anteriormente. Se pueden usar otras herramientas alternativas.