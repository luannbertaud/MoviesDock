```
Settings
└───Media Management
│   └───Folders
│   |   Delete empty folders
│   └───Importing
|   |   Minimum Free Space 1000Mb
|   |   Use Hardlinks -> false
|   |   Import Extra Files -> srt,sub,nfo
│   └───File Management
|   |   Analyse video files -> false
│   └───Permissions
|   |   Set Permissions
|   |   chmod Group -> {plex process user}
│   └───Root folders
|       /movies
|
└───Indexers
│   └───Indexers
|   │   └───New Indexer
|   |       {Name, Url, API Key from Jackett}
│   └───Restrictions
│        └───New Restriction
│        |   Must Not Contain -> "x265, h265, x.265, h.265, hevc"
│        └───New Restriction
│            Must Not Contain -> "DTS, .DTS, DTS-HD, .DTS-HD" 
|
└───Download Clients
    └───Download Clients
    │   └───New Deluge
    |       Name -> Deluge
    |       Category -> {empty}
    └───Completed Download Handling
        Remove

```