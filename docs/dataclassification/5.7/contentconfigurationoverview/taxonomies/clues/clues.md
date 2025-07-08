---
title: "Classification Rules (Clues)"
description: "Classification Rules (Clues)"
sidebar_position: 5
---

# Classification Rules (Clues)

Each taxonomy contains a set of terms. **Terms** are defined by set of configuration **rules** (also
called **clues**). Clues are used to describe the language found in documents, making these
documents belong to a particular topic.

## Predefined Classification Rules

The standard taxonomies provided with Netwrix Data Classification include predefined classification
rules for personally identifiable information (full name, home address, etc.). They are available in
the following languages:

- English
- French
- German
- Spanish

    ![predefined_clues](/img/product_docs/dataclassification/5.7/admin/taxonomies/predefined_clues.webp)

Users can easily extend the out-of-the-box classification rules by adding relevant keywords and
terms in other languages.

In addition, there are predefined classification rules for various national identification and
registration numbers. These rules typically look for ID patterns supplemented by related keywords
for better classification precision.

![clues_1](/img/product_docs/dataclassification/5.7/admin/taxonomies/clues_1.webp)

These rules are provided for the following countries (coverage varies):

- Australia
- Brazil
- Bulgaria
- Canada
- Denmark
- France
- Germany
- Hong Kong
- India
- Italy
- Netherlands
- Singapore
- South Africa
- Spain
- Sweden
- United Kingdom
- USA

## Working with Clues

To work with the clues, select the required subnode (terms set) under the taxonomy tree on the left
and then select Clues on the right:

![taxonomyclues_thumb_0_0](/img/product_docs/dataclassification/5.7/admin/taxonomies/taxonomyclues_thumb_0_0.webp)

- For each clue in the list, you can view and manage its type, score, and other properties.
- To add a new clue, go to the topmost row in the list and specify its properties.

## Documents count

Click the Doc Counts link in the top right corner to get the number of documents that match the word
/ phrase used within the clue:

![doccounts](/img/product_docs/dataclassification/5.7/admin/taxonomies/doccounts.webp)

## Suggested Clues

The suggested clues feature facilitates the process of tailoring classification rules in context by
offering relevant terms and keywords based on previously indexed file content. This feature is
available for all Latin script based languages with increased support for the languages that have
support for stemming and/or stop-word analysis:

- Afrikaans
- Danish
- Dutch
- English
- Finnish
- French
- German
- Hungarian
- Italian
- Norwegian
- Spanish
- Portuguese
- Romanian
- Swedish
- Welsh

See also:

[Types of Clues](/docs/dataclassification/5.7/contentconfigurationoverview/introduction/clues/cluestypes.md)

[Manage Clues](/docs/dataclassification/5.7/contentconfigurationoverview/introduction/clues/manageclues/manageclues.md)
