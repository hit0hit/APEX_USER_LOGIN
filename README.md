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
https://docs.oracle.com/en/database/oracle/apex/23.1/aeapi/CREATE_USER-Procedure.html#GUID-95721E36-4DAB-4BCA-A6F3-AC2BACC52A66

Aqui está um exemplo de resultado de consulta SQL a partir da tabela:

```sql
USER_NAME   | WORKSPACE_NAME
------------| --------------------
MCDONAC     | ASKTOM
ADMIN       | INTERNAL
MCDONAC     | MCDONAC

51.15 CREATE_USER Procedure

Syntax
APEX_UTIL.CREATE_USER (
    p_user_id                       IN NUMBER   DEFAULT NULL,
    p_user_name                     IN VARCHAR2,
    p_first_name                    IN VARCHAR2 DEFAULT NULL,
    p_last_name                     IN VARCHAR2 DEFAULT NULL,
    p_description                   IN VARCHAR2 DEFAULT NULL,
    p_email_address                 IN VARCHAR2 DEFAULT NULL,
    p_web_password                  IN VARCHAR2,
    p_web_password_format           IN VARCHAR2 DEFAULT 'CLEAR_TEXT',
    p_group_ids                     IN VARCHAR2 DEFAULT NULL,
    p_developer_privs               IN VARCHAR2 DEFAULT NULL,
    p_default_schema                IN VARCHAR2 DEFAULT NULL,
    p_allow_access_to_schemas       IN VARCHAR2 DEFAULT NULL,
    p_account_expiry                IN DATE     DEFAULT TRUNC(SYSDATE),
    p_account_locked                IN VARCHAR2 DEFAULT 'N',
    p_failed_access_attempts        IN NUMBER   DEFAULT 0,
    p_change_password_on_first_use  IN VARCHAR2 DEFAULT 'Y',
    p_first_password_use_occurred   IN VARCHAR2 DEFAULT 'N',
    p_attribute_01                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_02                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_03                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_04                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_05                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_06                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_07                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_08                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_09                  IN VARCHAR2 DEFAULT NULL,
    p_attribute_10                  IN VARCHAR2 DEFAULT NULL,
    p_allow_app_building_yn         IN VARCHAR2 DEFAULT NULL,
    p_allow_sql_workshop_yn         IN VARCHAR2 DEFAULT NULL,
    p_allow_websheet_dev_yn         IN VARCHAR2 DEFAULT NULL,
    p_allow_team_development_yn     IN VARCHAR2 DEFAULT NULL );


TABELAS
SELECT * FROM apex_workspace_apex_users WAU
INNER JOIN APEX_APPL_ACL_USERS AAU ON AAU.USER_NAME = WAU.USER_NAME
INNER JOIN APEX_APPL_ACL_USER_ROLES AUR ON AUR.USER_NAME = WAU.USER_NAME
INNER JOIN APEX_APPL_ACL_ROLES AAR ON AAR.ROLE_ID = AUR.ROLE_ID

Example 1
BEGIN
    APEX_UTIL.CREATE_USER(
        p_user_name    => 'NEWUSER1',
        p_web_password => 'secret99');
END;

Example 2
BEGIN
    APEX_UTIL.CREATE_USER(
        p_user_name                     => 'NEWUSER2',
        p_first_name                    => 'FRANK',
        p_last_name                     => 'SMITH',
        p_description                   => 'Description...',
        p_email_address                 => 'frank@smith.com',
        p_web_password                  => 'password',
        p_developer_privs               => 'ADMIN:CREATE:DATA_LOADER:EDIT:HELP:MONITOR:SQL',
        p_default_schema                => 'MY_SCHEMA',
        p_allow_access_to_schemas       => 'MY_SCHEMA2',
        p_change_password_on_first_use  => 'N',
        p_attribute_01                  => '123 456 7890');
END;
