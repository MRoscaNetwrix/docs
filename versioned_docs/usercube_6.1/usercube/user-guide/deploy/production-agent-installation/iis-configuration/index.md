# Configure the Pool and Site

This guide shows how to configure the application pool and website via IIS.

## Overview

IIS provides a platform for hosting and managing websites.
[See more details](https://learn.microsoft.com/fr-fr/iis/get-started/introduction-to-iis/introduction-to-iis-architecture).

To install the production agent, a website must be created and configured correctly, as part of an
application pool.

This page describes the optimal configuration in IIS to prepare the production agent's installation.

## Configure the Application Pool and Site

Configure the application pool and site by proceeding as follows:

1. Open IIS and remove the default site and pool.

    IIS can usually be found in Windows' search menu, or from Server Manager by accessing the
    **Tools** menu.

    ![IIS: Step 1](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_iis1.png)

2. Right-click on **Application Pools** to add a new pool named `Usercube`.

    ![IIS: Step 2](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_iis2.png)

3. Right-click on **Sites** to add a new site named `Usercube<Organization>`, make sure that the
   selected application pool is `Usercube` and set the `path` field to the `Runtime` folder.

    ![IIS: Step 3](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_iis3.png)

4. Right-click on the application pool to open its advanced settings and make sure that the
   following parameters are set as such:

    ![IIS: Step 4](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_iis4.png)

    ![IIS: Step 5](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_iis5.png)

5. Make sure that IIS contains an SSL certificate, by accessing the home page of IIS server and
   double-clicking on **Server Certificates**.

    If the certificate is not ready yet, generate an auto-signed certificate.

    ![IIS Server Certificate: Step 1](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_servercertificate1.png)

    If the certificate is not there yet, import it by clicking on **Import�** in the right-side
    menu, and specify the certificate's path and password.

    ![IIS Server Certificate: Step 2](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_servercertificate2.png)

6. Add the certificate's URL to the site by right-clicking on the site, selecting **Edit Bindings�**
   and clicking on **Add**, then choosing `https` as type, `443` as port, specifying the server's
   URL (without the `https` part) as host name, and finally selecting the server certificate.

    ![IIS Server Certificate: Step 3](/img/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/prodagent_servercertificate3.png)

    Click on **OK**.

    If the server's certificate is not available at this point, then make sure it was correctly
    imported in the previous step.

## Next Steps

To continue,
[set the right permissions on the working directory](/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/directory-permissions/index.md).
