---
sidebar_position: 3007
title: Dropbox
---

Filter: 

* All Files

Submit Search

# Dropbox

This section contains information on how to exclude Dropbox files or folders from being crawled.

## Configure Exclusions

You can define the list of file locations that will be ignored when indexing files in Dropbox, i.e. excluded from processing. All Dropbox documents start with *https://www.dropbox.com/home/* followed by the full path to the file. So, to exclude specific document, enter the full document URL. You can exclude all pages within a folder - for that, use a wildcard indicator (e.g. “*https://www.dropbox.com/home/Test Folder/\**”).

To configure exclusions, do the following:

1. In the management console, click **Content Configuration → Sources** → **Dropbox**, then in the left pane click Collection Exclusions.
2. Click **Add**.

   [![](../../../../../../../static/images/DataClassification_5.7/Content/Resources/Images/boxexclusions_thumb_0_0.png)](../../../../Resources/Images/boxexclusions.png)
3. Click **Filter** and in the **Filter** field specify the objects (files or folders) to exclude:

   To exclude a certain file, enter *https://www.dropbox.com/home/*.
   For example: *https://www.dropbox.com/home/Reports**/Test Document.docx*

   Wildcards can be used anywhere in the exclusion pattern definition as follows:

   * The asterisk character (\*) matching any sequence of characters
   * The question mark character (?) matching any single character

   For example:

   * **https://www.dropbox.com/home/*Test Folder/\** will exclude all documents in the folder
   * *\*/Restricted Folder/\** will exclude specific folder in any Dropbox source

**NOTE:** Exclusions are case-insensitive.

4. Optionally, enter a test path to verify the settings and click **Test**.

   If needed, you can use metadata conditions to restrict when an exclusion filter should be applied. For that, click **Condition** tab and click **Add**. Then select how the exclusion conditions will work: it can check if metadata field of the document has any value, is not specified, or matches a specific metadata value.

   | Criteria | Condition |
   | --- | --- |
   | Comparison | Compare a value in the document metadata field with the value set by condition. With this criteria selected, you will then need to specify:  * **Field name** — document metadata field to check * **Comparison** — operator to use (for example, "does not contain") * **Value** — value to compare against For example, to exclude documents tagged with year 2018, set the condition as follows:  * **Field Name** — *DocYear* * **Comparison** — *equals* * **Value** — *2018* |
   | Has any value | Exclude the document if its metadata field has any value. With this criteria selected, specify **Field Name**. |
   | Has no values | Exclude the document if metadata field value is not specified. With this criteria selected, specify **Field Name**. |

   When finished, click **Add**.
5. Finally, click **Save** and close the window.