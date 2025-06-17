# Outlook Mail Archive

The Outlook Mail Archive source configuration screen allows you to enable the crawling and
classification of content stored in PST files:

**NOTE:** If you wish to make other configuration changes before collection of the source occurs
ensure you tick the checkbox Pause source on creation.

![add_outlook](/img/versioned_docs/dataclassification_5.6.2/ndc/sources/exchange_mailbox/add_outlook.webp)

Multiple mailboxes can be added at one time via the "+" button. Collection will process all folders
/ emails / attachments within the mailbox - associating the attachment text with the respective
email.

Select documents' images processing mode:

- Disabled – documents' images will not be processed.
- Default – defaults to the source settings if configuring a path or the global setting if
  configured on a source.
- Normal – images are processed with normal quality settings.
- Enhanced – upscale images further to allow more.

Folders / Items can be excluded from processing via the Exchange Exclusions management screen.
