# Setup

First of all please create a `.env` file containing informations needed for the services.

The `.env.example` file gives you a template.

| Variable | Meaning |
|---------:|:-----|
|MVD_PMS_HOSTNAME | Name of the PlexMediaServer that will be created.|
|MVD_PMS_SERV_IP | IP where the PlexMediaServer can be found.|
|MVD_PMS_CLAIM_TOKEN | Plex claim token that can be found [here](https://www.plex.tv/claim), it will be used to auto-claim the Plex container server.|
|MVD_MOVIES_PATH | Path to the folder containing the movies that will be accessible by the Plex server.|
|MVD_DOWNLOADS_PATH | Path to the folder containing the movies that are currently being downloaded (before being moved to MVD_MOVIES_PATH).|
|MVD_CONFIG_PATH | Path to the folder containing the different configs of all **MoviesDock** services.|
|MVD_TIMEZONE | Timezone to set **MoviesDock** on.|

Then you can start **MoviesDock** by running `docker-compose up` at the root of the repository.


# Post config

Here is some settings I use to complete the configuration.


## Radarr
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

## Jackett
```
Settings
└───FlareSolverr
        {Url of FlareSolverr container, port 8191}

```