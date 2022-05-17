# Database Project for Azure SQL Database

Example of a SQL Server Database Project that deploys to an Azure SQL Database using GitHub Actions. Based on a blog post I wrote called 'Deploying to Azure SQL Database using GitHub Actions' (https://bit.ly/31PUTMV).

It uses a YAML pipeline, which is also known as a workflow in GitHub. You can find this file in the /.github/workflows folder of the repository.

In order to use it with GitHub Actions in your own account you can either import or fork this repository into another GitHub repository.

In order for the workflow to run the firewall settings for the logical SQL Server MUST allow Azure services and resources to access the server. Alternatively, add the Azure Login GitHub Action to this workflow https://github.com/marketplace/actions/azure-login.

In addition, you MUST have three secrets specified, any defaults in my repo are blank:

- AZURE_CREDENTIALS - Required to create a temporary firewall rule for your agent, follow link to [create the credential](https://bit.ly/3Mn5a53). 
- AZURESQLDB_SERVER, which contains your logical SQL Server name
- AZURESQLDB_CONNECTION_STRING, which contains connection string to your Azure SQL Database

This repository is provided "as is" based on the MIT license (https://opensource.org/licenses/MIT). Basically, I am not responsible for your use of it.
