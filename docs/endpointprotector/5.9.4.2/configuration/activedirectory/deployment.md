# Creating the Deployment GPO

To create the deployment Group Policy Objects (GPO), follow these steps:

**Step 1 –** Open the Group Policy Management console, right-click Group Policy Objects and click
New;

**Step 2 –** Add Endpoint Protector 32 bit as the GPO name;

**Step 3 –** Right-click the new GPO and click Edit;

![Creating the Deployment Group Policy Objects](/img/product_docs/endpointprotector/5.9.4.2/configuration/activedirectory/gpoeditor.webp)

**Step 4 –** Expand Computer Configuration / Software Settings and right-click Software
Installation, and then select New/Package;

**NOTE:** When browsing the ‘msi’ file, ensure it is located in a folder shared over your network
and accessible by the computers on your Active Directory.

![Configuring Deployment for Group Policy Objects](/img/product_docs/endpointprotector/5.9.4.2/configuration/activedirectory/gpoconfiguration.webp)

**Step 5 –** Close the Group Policy Object Editor console and repeat this step for the Endpoint
Protector 64-bit GPO.
