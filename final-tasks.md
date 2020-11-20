## Task One (50 points)

As an extension to the Web scenario, add a third endpoint to the Traffic Manager, to serve a content in a case of failure of both regions in Europe.
You have an East US 2 region available and static HTML file which must be served when Europe is down.
You can't use Virtual Machines.

HTML file content:

```
<p>Sorry we have an issue in Europe. We will back soon.</p>
<p>Your wonderful Team number XX</p>
```
## Task Two (150 points)

```
short note:
Managed Identity for VMData is enabled. VM have Virtual Machine Contributor rights on Resource Group level where it is deployed. 
```

VMdata VM have rights to manage other machines as well as itself.
Using Azure CLI, prepare a shell script that will deallocate a machine on which it is running.
As a confirmation of done, please commit your script to the GH repository.

Useful docs: https://docs.microsoft.com/en-us/azure/active-directory/managed-identities-azure-resources/ 