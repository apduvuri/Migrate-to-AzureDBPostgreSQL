# Migrate PostgreSQL instances to Azure Database for PostgreSQL - Flexible server

## About Azure Database for PostgreSQL - Flexible server

Azure Database for PostgreSQL - Flexible Server is a fully managed database service designed to provide more granular control and flexibility over database management functions and configuration settings. The service generally provides more flexibility and server configuration customizations based on user requirements. The Azure Database for PostgreSQL - Flexible Server architecture allows users to collocate the database engine with the client tier for lower latency and choose high availability within a single availability zone and across multiple availability zones. Azure Database for PostgreSQL - Flexible Servers also provide better cost optimization controls with the ability to stop/start your server and a burstable compute tier ideal for workloads that don't need full compute capacity continuously.

To learn more about Azure Database for PostgreSQL - Flexible server, you can refer to the official [documentation](https://learn.microsoft.com/en-us/azure/postgresql/flexible-server/overview). The documentation provides comprehensive information on how to create and manage your PostgreSQL database in the Azure cloud, including setup, configuration, scaling, security, and more.

## Overview of migration service in Azure Database for PostgreSQL

The migration service in Azure Database for PostgreSQL simplifies the process of moving your PostgreSQL databases to Azure, offering migration options from an Azure Database for PostgreSQL single server, AWS RDS for PostgreSQL, on-premises servers, and Azure virtual machines (VMs). The migration service is designed to help you move to Azure Database for PostgreSQL - Flexible Server with ease and confidence.

In this document, we provide a walk-through of how to perform migrations for different scenarios from your Azure Database for PostgreSQL-Single server/on-premises/IaaS/AWS to Azure Database for PostgreSQL - Flexible server in simple, efficient and a hassle-free way.

## Key Benefits

Key benefits of using the migration service are -  

* Managed migration service.
* No complex setup/pre-requisites required.
* Simple to use portal-based migration experience.
* Fast offline migration service.
* No limitations in terms of size of databases it can handle.
* Support for Schema and Data migrations

For more detailed information and guidance on using the migration service in Azure Database for PostgreSQL, please refer to the  documentation at [Migration Service](https://learn.microsoft.com/azure/postgresql/migrate/migration-service/concepts-migration-service-postgresql).

## Limitations

- For a comprehensive list of known issues and limitations related to the migration service in Azure Database for PostgreSQL, please refer to the official documentation - [Migration service in Azure Database for PostgreSQL](https://learn.microsoft.com/en-us/azure/postgresql/migrate/migration-service/concepts-known-issues-migration-service)
