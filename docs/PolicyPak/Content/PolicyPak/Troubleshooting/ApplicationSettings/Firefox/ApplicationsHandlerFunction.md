---
sidebar_position: 3953
title: 'Firefox: Why doesn''t the Firefox Applications Handler function work as expected?'
---

# Firefox: Why doesn't the Firefox Applications Handler function work as expected?

Managing Firefox with Netwrix Endpoint Policy Manager (formerly PolicyPak) enables you to dictate what external applications will open outside of Firefox. For instance opening up Adobe Reader instead of the internal reader, and so on.

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/163_1_asdcvvfgfg.jpg)

Here are some nuances of Firefox Application Handlers.

1. Some handlers are hard-coded. So, they are always shown in the UI, even if they are scheduled to be removed due to "REPLACE" mode.

Here is the list of hard-coded handlers:

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/163_2_2017-11-15_1433.png)

For example, if you set PPAM FF Pak handler setting to the following value:

```
MODE=REPLACE .zip, APP: C:\Program Files\7-Zip\7zFM.exe
```
So, you might expect the list would contain exactly one handler:

```
zip -> C:\Program Files\7-Zip\7zFM.exe
```
However the actual list which user gets is list of 5 handlers (Podcast, PDF, Video, Web, and ZIP) because some are always hardcoded.

2. Firefox prefers opening content internally to firing external programs whenever possible (e.g., to open those file types he is able to handle internally).

Content that can be handled internally includes images, texts, HTML and XML code, and content with some special meaning in Web (CSS, JS, etc.). The actual decision is made based on so-called MIME type, and not on file extension. In case of HTTP/HTTP surfing, Firefox usually uses MIME type returned in "Content-Type" response header:

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/163_3_2017-12-13_1413.png)

If MIME type is "text/plain", "text/html", "text/css", "image/jpeg", or any other special type file is opened internally. Even if "Content-Type" header is not set in web response, Firefox uses some sophisticated algorithm to guess MIME from actual content, and opens resource of special types internally.

For this reason, even though it is possible to add handlers for .JPG, .HTML, .HTM, .TXT, etc, and they appear in UI, Firefox will keep opening resources of such types internally.

The general rule of thumb here is the following: when there is no handler for the given type and Firefox normally shows "Open with dialog" for this type, it fires Application Handler for the same type when there is a handler:

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/163_4_2017-12-13_1422.png)

3. The actual behavior during Web surfing depends on MIME type for resource returned by Web-server.

Even though you can have handler for PDF (application/pdf), or ZIP (application/x-zip-compressed), or whatever, it might not work for resources returned with non-standard MIME type. If returned MIME types is generic type for binary resources (application/octet stream), or some type with no special meaning for Firefox (see #2), Firefox fires handler to open file like this:

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/163_5_2017-12-13_1433.png)

Otherwise file will be opened internally.

Actual MIME type returned in response depends on Web-Server and resource settings, and it's up to server to return "correct" MIME type.

The general rule of thumb here is similar to rule in #2. If Firefox shows "Open with dialog" when there is no handler for resource, it fires Application Handler for the same resource if there is one.