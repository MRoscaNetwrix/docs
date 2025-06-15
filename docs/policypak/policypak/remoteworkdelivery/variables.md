# What variables can I use in place for source or destination in Remote Work Delivery Manager?

The following variables are honored in Netwrix Endpoint Policy Manager (formerly PolicyPak) Remote
Work Delivery Manager.

Using the list below you can use these variables as sources or destinations.

For instance to copy files from `\\server2016\share` to `%DesktopDir%` simply put in `%DesktopDir%`
in the Destination slo:

![806_1_img](../../../../static/img/product_docs/policypak/policypak/remoteworkdelivery/806_1_img.jpg)

The acceptable variables are below. Be sure to encapsulate them all with %, like %DestopDir%

```
AppDataDir
CommonAppdataDir
CommonDesktopDir
CommonFavoritesDir
CommonProgramsDir
CommonStartMenuDir
CommonStartUpDir
Desktop
DesktopDir
Documents
DocumentsDir
Downloads
DownloadsDir
Favorites
FavoritesDir
Links
LinksDir
Music
MusicDir
NetPlacesDir
Pictures
PicturesDir
ProgramFilesDir
ProgramFilesX86Dir
ProgramFilesX64Dir
ProgramsDir
RecentDocumentsDir
SendToDir
StartMenuDir
StartUpDir
SystemDir
SystemX86Dir
Videos
VideosDir
DestinationDir
Destination
DestinationFile
```
