# Migrate IaaS/On-Premises/AWS PostgreSQL databases to Azure Database for PostgreSQL - Flexible server

Azure Database for PostgreSQL - Flexible Server is a fully managed database service designed to provide more granular control and flexibility over database management functions and configuration settings. The service generally provides more flexibility and server configuration customizations based on user requirements. The Azure Database for PostgreSQL - Flexible Server architecture allows users to collocate the database engine with the client tier for lower latency and choose high availability within a single availability zone and across multiple availability zones. Azure Database for PostgreSQL - Flexible Servers also provide better cost optimization controls with the ability to stop/start your server and a burstable compute tier ideal for workloads that don't need full compute capacity continuously.

In this article, we provide a walk-through of how to perform migrations from your Azure Database for PostgreSQL-Single server/on-premises/IaaS/AWS to Azure Database for PostgreSQL - Flexible server in simple, efficient and a hassle-free way.


## Key Benefits
Key benefits of using this service is -  

* Managed migration service.
* No complex setup/pre-requisites required.
* Simple to use portal-based migration experience.
* Fast offline migration service.
* No limitations in terms of size of databases it can handle.
* Support for Schema and Data migrations

## Using Migration runtime server

The Migration Runtime Server is a specialized feature within the [migration service in Azure Database for PostgreSQL](https://learn.microsoft.com/en-us/azure/postgresql/migrate/migration-service/concepts-migration-service-postgresql), designed to act as an intermediary server during the migration process.

- [**Introduction to Migration runtime server within migration service in Azure Database for PostgreSQL**](migration-service-Azure-DB-PostgreSQL/Migration-Runtime-Server/overview.md)

## Start your offline migration

Get started with the offline migration from on-premises/IaaS/AWS to Azure Database for PostgreSQL - Flexible server by using one of the following methods:

- [**Using the Azure ARM Template - Migrate from IaaS to Azure Database for PostgreSQL - Flexible server (Offline)**](migration-service-Azure-DB-PostgreSQL/Offline-Migrations/IaaS-to-Flexible-offline-migration-using-ARM-Template.md)

## Start your online migration

- Sign in to the Azure Portal at https://portal.azure.com.
- Search for "Preview features" in the Azure portal search bar.

![Go to preview features](migration-service-Azure-DB-PostgreSQL/media/readme_images/enable-preview-features.png)

- In the Preview features section, provide your Azure subscription details.
- Choose Microsoft.DBforPostgreSQL as the type.
- Select "Online migration for migration service in Azure Database for PostgreSQL" from the list.
- Click "Register" to get the access to the preview feature.

![Select Preview Feature](migration-service-Azure-DB-PostgreSQL/media/readme_images/enable-online-migration.png)

Get started with the online migration from on-premises/IaaS/AWS to Azure Database for PostgreSQL - Flexible server by using one of the following methods:

- [**Using the Azure CLI - Migrate from IaaS to Azure Database for PostgreSQL - Flexible server (Online)**](migration-service-Azure-DB-PostgreSQL/Online-Migrations/IaaS-to-Flexible-online-migration-using-cli.md)
- [**Using the Azure Portal - Migrate from IaaS to Azure Database for PostgreSQL - Flexible server (Online)**](migration-service-Azure-DB-PostgreSQL/Online-Migrations/IaaS-to-Flexible-online-migration-using-portal.md)


## Current Limitations [Preview Mode]
* You can select a max of eight databases in one migration attempt. If you've more than eight databases, you must wait for the first migration to be complete before initiating another migration for the rest of the databases. Support for migration of more than eight databases in a single migration will be introduced later.
* The service doesn't migrate users and roles.
* Manual validation of the data, PostgreSQL objects in target server post migration.
* The tool only migrates user databases and not system databases like template_0, template_1.
* Migration of POSTGIS, TIMESCALEDB, POSTGIS_TOPOLOGY, POSTGIS_TIGER_GEOCODER, PG_PARTMAN extensions are not supported from source to target. 
* Extensions that are not supported in the Azure Database for PostgreSQL – Flexible server cannot be migrated. Supported extensions in PostgreSQL Flexible server are - [Extensions - Azure Database for PostgreSQL - Flexible Server | Microsoft Learn](https://learn.microsoft.com/en-us/azure/postgresql/flexible-server/concepts-extensions)
* Certain collations are not supported for migrations into Azure Database for PostgreSQL – Flexible server. Please contact Microsoft team, for failures in migrations related to Collations.
* User-defined collations cannot be migrated into Azure Database for PostgreSQL – Flexible server.
* Superuser is not supported in Azure Database for PostgreSQL – Flexible server. Below are the few statements that are not supported in the PostgreSQL flexible server – 
    * Alter user `<<username>>` with SUPERUSER;
    * Create casts
    * Creation of FTS parsers and FTS templates
    * Users with superuser roles
    * `SSLMODE values supported are prefer, require` for migration. Different SSLMODE like verify-ca, verify-full will be supported in the future releases.
