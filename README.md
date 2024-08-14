# Database Project for Azure SQL Database

Example of a SQL Server Database Project that deploys to an Azure SQL Database using GitHub Actions. Based on a blog post I wrote called '[Deploying to Azure SQL Database using GitHub Actions](https://bit.ly/31PUTMV)' .

A brief overview is below. However, there is also a [wiki for this repository](https://github.com/kevchant/GitHub-AzureSQLDatabase/wiki). .

It contains three different workflows in GitHub (those from an Azure DevOps background can think of workflows as YAML Pipelines). One for a standard install using sql-action v1, one uses sql-action v2 and another one connects to Azure KeyVault. You can find the files for the three different workflows you can use in the [/.github/workflows](https://github.com/kevchant/GitHub-AzureSQLDatabase/tree/main/.github/workflows) folder of the repository.

In order to use it with GitHub Actions in your own account you can either import or fork this repository into another GitHub repository.

In order for the workflows to run the firewall settings for the logical SQL Server MUST allow Azure services and resources to access the server. Alternatively, add the [Azure Login GitHub Action](https://github.com/marketplace/actions/azure-login) to this workflow .

You MUST have two secrets specified if using the Single-Azure-SQL-Database-KeyVault workflow, any defaults in my repo are blank:

- AZURE_CREDENTIALS - Required to create a temporary firewall rule for your agent, follow link to [create the credential](https://bit.ly/3Mn5a53). 
- AZURE_KEYVAULT, URL for your your Azure KeyVault

Plus, the below secrets must be in KeyVault:

- AzureSQLServer - Name of your logical SQL Server. 
- AzureSQLDB-Connection-String - Connection string to your Azure SQL Database.

If using the Single-Azure-SQL-Database workflow instead you MUST have three secrets specified , any defaults in my repo are blank:

- AZURE_CREDENTIALS - Required to create a temporary firewall rule for your agent, follow link to [create the credential](https://bit.ly/3Mn5a53). 
- AZURESQLDB_SERVER, which contains your logical SQL Server name
- AZURESQLDB_CONNECTION_STRING, which contains connection string to your Azure SQL Database

This repository is provided "as is" based on the MIT license (https://opensource.org/licenses/MIT). Basically, I am not responsible for your use of it.
