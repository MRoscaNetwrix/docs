# Taxonomy Settings Panel

The Taxonomy Settings panel displays the parameters of the top-level taxonomy selected in the Search (for example, File Size).

![taxonomysettings](../../../../../static/img/product_docs/dataclassification/ndc/admin/taxonomies/taxonomysettings.webp)

| Option | Description |
| --- | --- |
| Content Filters | This field allows the taxonomy to be restricted based on a booleanfilter (e.g. using the “CSE-FOLDERS” field) or any of the 8 document id filters. See the associated design guide for more information about the ContentFilter field in the Taxonomies table.  Valid entries include:   - <booleanfilter>cse-folders= http://www.bbc.co.uk/sport/</booleanfilter>(only process documents from this path) - <booleanfilter>NOT cse-folders=http://www.bbc.co.uk/sport/</booleanfilter>  (exclude documents from this path) - <booleanfilter>Author=Truman Capote</booleanfilter>  (only process documents by this author) - <documentidfilter>2</documentidfilter>  (only process documents with this DocumentID value) - <documentid4filter>3,77,890</documentid4filter>  (only process documents with one of these DocumentID4 values)   Note that any number of entries can be combined by concatenation into a single string.  Multiple restrictions of the same type are ORed together, so if multiple “cse-folders” entries exist then the document will pass if it matches any one of them.  Multiple restrictions of different types are ANDed together, so if multiple types exist then the document must pass all of them in order to get classified. |
| Max Categories | Sets the maximum number of classes from this taxonomy that will be allocated to each document. To set the Max Categories value across all taxonomies use the Settings tab in Index Manager. |
| Default Threshold | Sets the default threshold for newly created terms within the selected taxonomy (does not affect existing terms). |
| Create Default Clues | This setting controls the creation of default clues when. If enabled then a default clue is added to all Classes based on the title of the class – or, optionally based on the default metadata clue format. |
| Default Clue Score | Sets the default score value for new clues. |
| Default Metadata Clue | Specifies the format of a default metadata clue. This can be used to create automatic “self-referential” clues, as well as static assignments based on the term name in the document metadata. “[TermName]” can be utilised for a dynamic lookup of the classes name. |
| Count Mode | Sets the display mode for counts in the treeview. |
| Show Empty Nodes | Sets the display mode for empty nodes in the treeview. |
| Synchronise Termset | Enables/Disables automatic synchronisation through the TermStoreManager tool for the whole Term Set. |
