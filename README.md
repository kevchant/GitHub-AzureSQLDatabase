# Database Project for Azure SQL Database

Example of a SQL Server Database Project that deploys to an Azure SQL Database using GitHub Actions.

It uses a YAML pipeline, which is in the /.github/workflows folder.

In order to use it in GitHub Actions you can either import or fork this repository into another GitHub repository.

In order for the workflow to run the firewall settings for the logical SQL Server MUST allow Azure services and resources to access the server. Alternatively, add the Azure Login GitHub Action to this workflow https://github.com/marketplace/actions/azure-login.

In addition, you MUST have two secrets specified, defaults in my repo are blank:

- AZURESQLDB_SERVER, which contains your logical SQL Server name
- AZURESQLDB_CONNECTION_STRING, which contains connection string to your Azure SQL Database

This repository is provided "as is" based on the MIT license (https://opensource.org/licenses/MIT). Basically, I am not responsible for your use of it.
