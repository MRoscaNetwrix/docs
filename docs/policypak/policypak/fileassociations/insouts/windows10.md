# Managing Windows 10 File Associations with the In-Box Method

If you did not 't have Endpoint Policy Manager File Associations Manager, you could still manage file associations on Windows 10 and later. However, the process can be difficult and is not particularly user-friendly.

__NOTE:__ The following steps outline what you could do without Endpoint Policy Manager File Associations Manager. Do not perform these steps with Endpoint Policy Manager File Associations Manager because this will result in conflicts.

The following is the Microsoft-sanctioned way to establish file associations for Windows 8.1 and Windows 10:

__Step 1 –__ Create machine with all applications you might need.

__Step 2 –__ Correctly set all of the file associations.

__Step 3 –__ Use the built-in command ```DISM``` and export the associations to an XML file. The command would be something like:

```
Dism /Online /Export-DefaultAppAssociations:<XML path>\AppAssoc.xml
```

__Step 4 –__ Use Group Policy to ensure that specific computers use this XML file.

The exported file from this process might look something like this:

![about_policypak_file_associations_2](/static/img/product_docs/policypak/policypak/fileassociations/insouts/about_policypak_file_associations_2.png)

__Step 5 –__ Next, you would use the Group Policy setting called __Set a default associations configuration file__.

![about_policypak_file_associations_3](/static/img/product_docs/policypak/policypak/fileassociations/insouts/about_policypak_file_associations_3.png)

The disadvantages of using the in-box method for Windows 10 are as follows:

- You need a perfectly set machine for each new application deployment
- You will likely need different exported XML files, one for each different machine or organization type
- You might need to segment your computers into different organizational units (OUs) if you have different associations
- You need to follow this process even if you have just one or two applications you want to map
- To get the best experience, you need to do this for all associations a user is ever going to click on
- The entire XML file must be perfect and not have any variations

In summary,

- When your needs change, there is nothing dynamic about the process
- This process is entirely manual
- This process requires a lot of effort to build the perfect machine for each different computer group, export the files one by one for each group, and ensure all computers get the correct file

All this becomes time consuming every time you update and roll out an application that will be the registered extension or protocol.
