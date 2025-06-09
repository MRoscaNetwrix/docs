# How do I enable a STANDARD USER to see the COMPUTER SIDE RsOP ?

If asked by support for a GPRESULT /R GPRESULT /H or GPRESULT /X report, the default behavior of Active Directory is to only show the USER SIDE of the RSOP, and not the COMPUTER SIDE.

If you attempt to grab BOTH, or explicitly try to grab the COMPUTER side, you will NOT see the COMPUTER SIDE and/or get ACCESS DENIED like this.

![560_1_img-01_950x275](/img/product_docs/policypak/policypak/troubleshooting/560_1_img-01_950x275.jpg)

There is an easy temporary (or, if you wish) a permanent workaround.

Locate where the COMPUTER is within an OU. (Specific OU or any TOP LEVEL OU which contains the computer is fine.)

In my example, the computer is in East Sales Desktops. Then in the GPMC click DELEGATION, choose READ GROUP POLICY RESULTS DATA, then click ADD.

![560_3_img-02](/img/product_docs/policypak/policypak/troubleshooting/560_3_img-02.jpg)

Then add the USER or a GROUP the user is in. In this case I'm added EASTSALESUSER1 or you can add, for instance, AUTHENTICATED USERS.

![560_5_img-03](/img/product_docs/policypak/policypak/troubleshooting/560_5_img-03.png)

The final results before testing should look like this (where the USER (or GROUP) can now see the COMPUTER side RSOP..)

![560_7_img-04](/img/product_docs/policypak/policypak/troubleshooting/560_7_img-04.jpg)

The final result will be that THIS USER can now see the COMPUTER SIDE RSOP.

![560_9_img-05](/img/product_docs/policypak/policypak/troubleshooting/560_9_img-05.jpg)
