# <img src="/ultimate_plex_stack_transparent_bg.png" width="300px" alt="The Ultimate Plex Stack"></img>

Welcome to my stack repository! This repository showcases my docker compose setup for managing various media-related services using Docker containers. The compose file is meant to be modifed to each users liking as I know, not everyone has the same requirements. Hope you enjoy!

## Overview

**Docker Compose** Includes:

- **Plex:** Media server for streaming movies and TV shows.
- **Radarr:** Movie management and automation.
- **Sonarr:** TV show management and automation.
- **Prowlarr:** Indexer manager for Radarr and Sonarr.
- **Seerr:** Request management and monitoring for Plex.
- **Qbittorrent:** BitTorrent client with VPN support.
- **Tautulli:** Analytics and monitoring for Plex.
- **Autobrr:** Used to grab torrents immediately as they are released.
- **Wizarr:** Used to create links that can be sent to users so they can be invited to your media server.
- **Prefetcharr:** Automatically download the next episode in the series.

## Tutorial Video
[Watch my step-by-step tutorial on Youtube](https://www.youtube.com/watch?v=Uot_rs8qz2g)

## Dependencies

1. Linux
2. Docker / Docker Compose
3. OPTIONAL: Portainer - Docker GUI

## How to Use

1. Clone this repository / Copy the docker-compose.yml file:

   ```
   git clone https://github.com/DonMcD/ultimate-plex-stack.git
   ```
2. Fill in the required environment variables
3. Then enter the command ``` docker compose up -d ``` | or click deploy in Portainer

## Example of Environment variables in Portainer
* Check the .env file for more examples

<img width="657" alt="image" src="https://github.com/DonMcD/ultimate-plex-stack/assets/90471623/9a614eb0-8ff7-4eb9-b154-61c08cd595e9">

Keep in mind some variable names have changed since this screenshot was taken
  
File location examples:
- {MEDIA_SHARE} = /data
- {BASE_PATH} = /home/{username}/docker

To allow hardlinking to work (which you will definitely want!) you will have to use the same root folder in all of your container path. In this example we use "/data", so in the container it will look like "/data/downloads/tv"

An example of my folder structure:  
![image](https://github.com/DonMcD/ultimate-plex-stack/assets/90471623/2003ac26-a929-4ff6-ad67-e35fc51fb51a)
  
- Feel free to expand your folders to also include "books" or "music" as you need for your setup
  
  
1. In Radarr you will want to set your category to "movies", this will create the movies folder
2. In Sonarr you will want to set your category to "tv", this will create the tv folder

  
Anytime you reference your media folder in a container you want the path to look like /share/media/tv instead of /tv like a lot of the default guides say, if you do end up mapping the path as /tv hardlinking will not work

## Possible Additions

1. Organizr - Creates a lovely dashboard to help navigate to all of your apps
2. Portainer - Docker GUI
3. UptimeKuma - Gives you the ability to monitor your services

