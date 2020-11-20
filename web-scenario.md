# Stage 1

1. Create two virtual networks in Azure. One in West Europe and second in North Europe. Name it VNET1 and VNET2 (10 points)
2. Create 2 Ubuntu OS (18.04 LTS) VMs in Azure, sized to Standard_B1ls without Public IP Addresses in West Europe region. VMs need to be in an Availability Set. Name it VM1 and VM2. Availability Set name - ASwest (75 points)
3. Create 2 Ubuntu OS (18.04 LTS) VMs in Azures sized to Standard_B1ls without Public IP Addresses in North Europe region. VMs need to be in an Availability Set. Name it VM3 and VM4. Availability Set name - ASnorth (75 points)
4. Create a public Azure Load Balancer (Basic tier) in West Europe region and place it on front of two VMs you already created in the same region. Name it ALBwest .
5. Create a public Azure Load Balancer (Basic tier) in North Europe region and place it on front of two VMs you already created in the same region. Name it ALBwest.
6. Create the Azure Traffic Manager profile to ensure a disaster recovery for Weest Europe-placed VMs in North Europe region with automatic failover in case of West Europe-placed VMs unavailability.
7. Ensure that the incoming traffic to the VMs (on the Load Balancers public IPs) is prohibited (not open for anyone) - use LB rules to prohibit traffic. (10 points)
8. Shut down the VMs (10 points)

Usefull docs: https://docs.microsoft.com/en-us/azure/

# Stage 2

1. Power-up the VMs You created in previous stage (10 points)
2. Create a NAT rules on Azure Load Balancers to have a possibility to login to VMs' using SSH (20 points)
3. Install Docker CE on all 4 VMs (10 points)
4. Run .Net 5 sample app as a daemon using Docker on Your Ubuntu 18.04 LTS VM running in Azure (https://hub.docker.com/_/microsoft-dotnet-samples) (50 points)
    1. .Net 5 sample app need to be running as user without administrative privileges when running in Docker (25 points)
    2. .Net 5 sample app need to be started after VM restart automatically (25 points)
5. Install NGINX reverse proxy to ensure .Net 5 sample app to be served on port 80 on every VM you created before (25 points)
6. Open the port 80 on Azure Load Balancers and configure Azure Traffic Manager properly to ensure local High Availability for .Net 5 sample app and reginal Disaster Recovery for it. (20 points)
7. Remove the NAT rules on Azure Load Balancers to have a possibility to login to VMs' using SSH (10 points)
8. Document the failover process with screenshots and description in english, saving it in MD format on GitHub (50 points)
