# tc-sql-raulmolina
Team Challenge sql - The Bridge.

### Estructura del repositorio

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
│       ├── 01_CREATES.sql
│       ├── 02_generate_data.ipynb
│       └── 03_queries_verification.ipynb
├── .env.example
├── .gitignore
├── README.md
└── requirements.txt
```

### BBDD Oracle XE

* Descargar Oracle XE:
* Descargar SQL*DEVELOPER
* Creación de BBDD. Ejemplo:
  * Conectar con usuario SYS as SYSDBA y SID XE.
  * Ejecutar script de creación

    ```
    -- 1. Permite crear usuarios sin el prefijo C## en la sesión actual
    ALTER SESSION SET "_ORACLE_SCRIPT" = true;

    -- 2. Crea tu usuario (sustituir XXXXXX por el password)
    CREATE USER TC03SQLBRIDGE IDENTIFIED BY XXXXXXXX;

    -- 3. Dale los permisos necesarios para trabajar
    GRANT CONNECT, RESOURCE, DBA TO TC03SQLBRIDGE;
    ALTER USER TC03SQLBRIDGE QUOTA UNLIMITED ON USERS;
    ```