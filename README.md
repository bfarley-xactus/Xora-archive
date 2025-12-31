# Xora-archive
Historical code and infrastructure from 2024-2025

# Current Production App Service - Configuration

## 1. Basic metadata
- Subscription: Universal Credit Services CSP-XCT
- Resource group: xactus-xora-prd-eastus-rg-01
- App Service name: xactus-xora-prd-eastus-appservice-01
- Region: East US 
- App Service Plan name: xactus-xora-prd-eastus-appserviceplan-01 (B3: 1)
- App Service Plan SKU: Basic B3
- Default Domain: xactus-xora-prd-eastus-appservice-01.azurewebsites.net

## 2. Runtime / Docker configuration
- Runtime stack: 
- Docker image & tag: compliance; latest
- Image source: Azure Container Registry
- Registry (ACR) name: xactuscontainers
- Startup command: /usr/local/bin/init.sh
- Authentication: Managed Identity; Identity: credentialingApp
- Deployment slot used for prod: No

## 3. App settings (environment variables)
- CLIENT_ID
- CLIENT_SECRET
- DOCKER_ENABLE_CI
- DOCKER_REGISTRY_SERVER_PASSWORD
- DOCKER_REGISTRY_SERVER_URL
- DOCKER_REGISTRY_SERVER_USERNAME
- MICROSOFT_PROVIDER_AUTHENTICATION_SECRET
- OFAC_API_KEY
- PORT
- SP_HOST
- SP_SITE_RELATIVE
- SQL_DATABASE
- SQL_PWD
- SQL_SERVER
- SQL_UID
- TENANT_ID
- TOKEN
- WEBSITE_HTTPLOGGING_RETENTION_DAYS
- WEBSITES_CONTAINER_START_TIME_LIMIT
- WEBSITES_ENABLE_APP_SERVICE_STORAGE
- WEBSITES_PORT

## 4. Connection strings
- sql server:     Driver={ODBC Driver 18 for SQL Server};Server=SQL_SERVER,1433;Database=SQL_DATABASE;Uid=sql_admin;Pwd=SQL_PWD;Encrypt=yes;TrustServerCertificate=no;Connection Timeout=30;)

## 5. Identity & secrets
- System-assigned identity: disabled
- User-assigned identities: credentialingapp
- Key Vault references used: no

## 6. Networking & access control
- VNet integration:
- Private endpoints: 0 private endpoints
- Access restrictions (IP rules, service endpoints): Enabled with no access restrictions
- Authentication/authorization:

## 7. Custom domains & certificates
- Domain names: xactus-xora-prd-eastus-appservice-01.azurewebsites.net
- TLS/SSL certificates:
- HTTPS only: (yes/no)

## 8. Scaling & availability
- Scale out rules: manual 1 instance
- Always On: yes
- Health checks / ping path:
- Backup configuration: Automatic backup, Every 1 hour

## 9. Deployment configuration
- Source (GitHub Actions, ACR, etc.): Container Registry
- Deployment slots:
- Relevant GitHub repos/workflows:

## 10. Dependencies
- Databases: Azure SQL xactus-xora-dev-eastus-sqlsrv-01
- Storage accounts:
- Queues, service bus, etc.:


