# APEX_USER_LOGIN


# Descrição da Tabela SQL para `apex_workspace_apex_users`

Este README fornece informações sobre a tabela SQL `apex_workspace_apex_users`, juntamente com um exemplo de resultado de consulta.

## Descrição da Tabela

A seguir está uma descrição da tabela SQL `apex_workspace_apex_users`:

| Name                  | Null?    | Type                  |
|-----------------------| -------- | ----------------------|
| WORKSPACE_ID          | NOT NULL | NUMBER                |
| WORKSPACE_NAME        | NOT NULL | VARCHAR2(255)        |
| WORKSPACE_DISPLAY_NAME|          | VARCHAR2(4000)       |
| FIRST_SCHEMA_PROVISIONED | NOT NULL | VARCHAR2(128)   |
| USER_NAME             | NOT NULL | VARCHAR2(100)        |
| FIRST_NAME            |          | VARCHAR2(255)        |
| LAST_NAME             |          | VARCHAR2(255)        |
| EMAIL                 |          | VARCHAR2(240)        |
| DATE_CREATED          | NOT NULL | DATE                  |
| DATE_LAST_UPDATED     | NOT NULL | DATE                  |
| AVAILABLE_SCHEMAS     |          | NUMBER                |
| IS_ADMIN              |          | VARCHAR2(12)          |
| IS_APPLICATION_DEVELOPER |      | VARCHAR2(12)       |
| ACCOUNT_LOCKED        |          | VARCHAR2(3)           |
| DESCRIPTION           |          | VARCHAR2(240)         |
| PASSWORD_VERSION      | NOT NULL | VARCHAR2(20)          |
| ACCOUNT_EXPIRY        |          | DATE                  |
| FAILED_ACCESS_ATTEMPTS |         | NUMBER                |
| PROFILE_IMAGE_NAME    |          | VARCHAR2(100)         |
| PROFILE_MIMETYPE      |          | VARCHAR2(255)         |
| PROFILE_FILENAME      |          | VARCHAR2(255)         |
| PROFILE_CHARSET       |          | VARCHAR2(128)         |

## Exemplo de Resultado de Consulta

Aqui está um exemplo de resultado de consulta SQL a partir da tabela:

```sql
USER_NAME   | WORKSPACE_NAME
------------| --------------------
MCDONAC     | ASKTOM
ADMIN       | INTERNAL
MCDONAC     | MCDONAC
