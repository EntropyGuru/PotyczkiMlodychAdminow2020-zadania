# Stage 1

1. Create a virtual network in Azure. Name it VNETdata (50 points)
2. Create a Ubuntu OS (18.04 LTS) VM in Azure, sized to Standard_B2s with Public IP Address attached to the VM's NIC. Name it VMdata (50 points)
3. Ensure that the incoming traffic to the VM (on public IP) is prohibited (not open for anyone) - use Network Security Group (NSG) to prohibit traffic. (10 points)
4. Shut down the VM (10 points)
5. Create an Azure Storage Account with Canonical File System (Azure Data Lake Gen 2) (50 points)
6. Upload this file to the Azure Data Lake Storage gen 2: https://www.stats.govt.nz/assets/Uploads/Business-price-indexes/Business-price-indexes-June-2020-quarter/Download-data/business-price-indexes-june-2020-quarter-csv-corrected.csv (10 points)

Useful docs: https://docs.microsoft.com/en-us/azure/

# Stage 2

1. Power-up the VM You created in previous stage (10 points)
2. Open incoming port 22 to the VM for your outgoing public IP address using NSG. (10 points)
3. Install Docker CE on the VM (10 points)
4. Run Dremio as a daemon using Docker on Your Ubuntu 18.04 LTS VM running in Azure (https://hub.docker.com/r/dremio/dremio-oss/) (50 points)
    1. Dremio need to use persistent storage when running in Docker (25 points)
    2. Dremio need to be running as user without administrative privileges when running in Docker (25 points)
    3. Dremio need to be started after VM restart automatically (25 points)
5. Open the incoming port 9047 in NSG to open Web access to Dremio (10 points)
6. Ensure that Dremio is up and running. Create Admin Account. (10 points)
7. Additional points will be added to the team that will install NGINX Reverse Proxy and configure it for using Dremio web panel on port 80 with success on querying Azure Data Lake Gen2 (hint: check web sockets connectivity!)
    1. Install NGINX web proxy to serve Dremio web panel om port 80 (25 points)
    2. Close the incoming port 9047 and open port 80 on NSG (10 points)
8. Configure Dremio to connect to Azure Data Lake Storage Gen 2 you created in Stage 1 (25 points)
9. Query CSV file you uploaded in Stage 1 to Azure Data Lake Storage Gen 2 in Stage 1 for all rows and create a screenshot from this operation. (25 points)
10. Attach it to the task reported as done and provide login as password to Dremio account in a secure way. (25 points)
