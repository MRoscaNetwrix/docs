# How do I add the SCCM Software Center to the Start Screen or Taskbar?

![724_1_hf-936-img-01](/img/product_docs/policypak/policypak/startscreentaskbar/724_1_hf-936-img-01.png)

The normal shortcut for the SCCM Software Center looks like this; but Netwrix Endpoint Policy Manager (formerly PolicyPak) Start Screen & Taskbar Manager doesn't support this kind of link.

However, you can perform the following steps instead to get the same effect.   
Using Endpoint Policy Manager Start Screen or Endpoint Policy Manager Taskbar Manager, create a link for a Custom application like this…

![724_3_hf-936-img-02](/img/product_docs/policypak/policypak/startscreentaskbar/724_3_hf-936-img-02.jpg)

Then, point it toward

```%SYSTEMROOT%\CCM\SCClient.exe page=AvailableSoftware```

Like what's seen here.

![724_5_hf-936-img-03](/img/product_docs/policypak/policypak/startscreentaskbar/724_5_hf-936-img-03.jpg)

__NOTE:__ If you don't like that page, you can pick a page… (NOT TESTED, but should work.) Special keywords can be found at this link. [https://www.prajwaldesai.com/create-shortcuts-for-configmgr-software-center/#:~:text=By%20default%20you%20will%20find,%5CCCM%5CSCClient.exe](https://www.prajwaldesai.com/create-shortcuts-for-configmgr-software-center/#httpswwwprajwaldesaicomcreate-shortcuts-for-configmgr-software-centertextBy20default20you20will20find5CCCM5CSCClientexe). Finally, take the defaults… and/or change the ShortCut name to suit.

![724_7_hf-936-img-04](/img/product_docs/policypak/policypak/startscreentaskbar/724_7_hf-936-img-04.jpg)

Final results should look like this…

![724_9_hf-936-img-05](/img/product_docs/policypak/policypak/startscreentaskbar/724_9_hf-936-img-05.jpg)
