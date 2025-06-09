# Additional Configuration

This section contains information on additional and / or optional tabs. Review the following for additional information:

| Tab | Description |
| --- | --- |
| Graph | The Graph tab shows a graphical representation of classification intersection points.  [![taxonomygraph_thumb_0_0](/img/product_docs/dataclassification/ndc/admin/taxonomies/taxonomygraph_thumb_0_0.png)](/docs/dataclassification/resources/images/taxonomygraph.png)  In the example above 6721 documents are tagged with "Medium (100kb-1Mb)", 1254 of these documents are also tagged with "HTML". It's also possible to see that there are 3517 documents that are tagged with both "HTML" and "English" (highlighted by the dashed links). |
| Info | The Info tab displays the term description (aka Scope Notes) for each preferred term. The Description field is often populated automatically when an external taxonomy is imported automatically using the Scope Notes. |
| Logs | All changes made to a term are recorded. The change history may be viewed from the Logs Tab:  ![termlogs](/img/product_docs/dataclassification/ndc/admin/taxonomies/termlogs.png) |
| User Edits | When auto-classifications are amended in SharePoint the user edits are recorded in the SQL database, these can later be reviewed to identify terms that require review:  ![useredits](/img/product_docs/dataclassification/ndc/admin/taxonomies/useredits.png) |
| User Suggestions | An optional interface can be enabled to allow users to suggest new terms for the termset hierarchy (http://netwrixdataclassificationserver/conceptQS/Taxonomies/TermSuggest.aspx).  Suggestions can trigger automatic notifications to taxonomy administrators, as well as being recorded in the database for later review on the "User Suggestions" tab:  [![usersuggestions_thumb_0_0](/img/product_docs/dataclassification/ndc/admin/taxonomies/usersuggestions_thumb_0_0.png)](/docs/dataclassification/resources/images/usersuggestions.png) |
