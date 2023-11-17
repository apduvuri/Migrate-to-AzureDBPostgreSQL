# Migrate IaaS/On-Premises PostgreSQL databases to Azure Database for PostgreSQL - Flexible server

Azure Database for PostgreSQL - Flexible Server is a fully managed database service designed to provide more granular control and flexibility over database management functions and configuration settings. The service generally provides more flexibility and server configuration customizations based on user requirements. The flexible server architecture allows users to collocate the database engine with the client tier for lower latency and choose high availability within a single availability zone and across multiple availability zones. Flexible servers also provide better cost optimization controls with the ability to stop/start your server and a burstable compute tier ideal for workloads that don't need full compute capacity continuously.

In this article, we provide a walk-through of how to perform migrations from your on-premises/IaaS to Azure Database for PostgreSQL - Flexible server in simple, efficient and a hassle-free way.


## Key Benefits
Key benefits of using this service is -  

* Managed migration service.
* No complex setup/pre-requisites required.
* Simple to use portal-based migration experience.
* Fast offline migration service.
* No limitations in terms of size of databases it can handle.
* Automatically, spin up a purpose-built docker container in the target Azure Database for PostgreSQL - Flexible server and drive the incoming migrations.
* Support for Schema and Data migrations


## Start your offline migration
Get started with the offline migration from on-premises/IaaS to Azure Database for PostgreSQL - Flexible server by using one of the following methods:

* [**Using the Azure CLI - Migrate from IaaS to Azure Database for PostgreSQL - Flexible server (offline)**](./IaaS-to-Flexible-offline-migration-using-cli.md)
* [**Using the Azure Portal - Migrate from IaaS to Azure Database for PostgreSQL - Flexible server (offline)**](./IaaS-to-Flexible-offline-migration-using-portal.md)
* [**Using the Azure CLI - Migrate from AWS RDS PostgreSQL to Azure Database for PostgreSQL - Flexible server (offline)**](./AWSRDS-to-Flexible-offline-migration-using-cli.md)
* [**Using the Azure ARM Template - Migrate from IaaS to Azure Database for PostgreSQL - Flexible server (offline)**](./IaaS-to-Flexible-online-migration-using-ARM-Template.md)


## Current Limitations [Preview Mode]
* You can have only one active migration to your flexible server.
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
    * `SSLMODE=prefer` is the only mode supported for migration. Different SSLMODE like require, disable, verify-full will be supported in the future releases.
