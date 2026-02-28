<img width="400" alt="image" src="https://github.com/user-attachments/assets/c791abbc-8503-4cd6-af4c-e5ad842deb78" />

Welcome to my media stack repository! This repository showcases my docker compose setup for managing various media-related services using Docker containers. The compose file is meant to be modifed to each users liking as I know, not everyone has the same requirements. Hope you enjoy!

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

<img width="1546" height="294" alt="env_example_photo" src="https://github.com/user-attachments/assets/03b7d5d0-ac8f-425d-9cf4-7fe08d9e9e9d" />

  
## File Locations
- {MEDIA_SHARE} = /data
- {BASE_PATH} = /home/{username}/appdata

To allow hardlinking to work (which you will definitely want!) you will have to use the same root folder in all of your container paths. In this example we use "/data", so in the container, the path will look like "/data/downloads/tv"

## Example of the Folder Structure (Required for Hardlinking):  
<img width="902" height="440" alt="image" src="https://github.com/user-attachments/assets/4ae596da-cda8-452c-aaa4-431cc10b5da8" /><br>

*Anytime you reference a storage location you will always use ```/data/media/movies``` or ```/data/downloads/movies``` not just ```/movies```
  
- Feel free to expand your folders to also include "books" or "music" as you need for your setup

## Setting File Permissions
Use ``` sudo chmod 777 -R /data ``` and ``` sudo chmod 777 -R /home/donny/appdata ``` to open your permissions up and allow the docker containers to interact with your folders.

## Tips
1. In Radarr you will want to set your category to "movies" under the "Add Download Client" menu.
<img width="677" height="224" alt="image" src="https://github.com/user-attachments/assets/2340bec1-cf7b-4b7f-a599-0a63dcb65308" />

2. In Sonarr you will want to set your category to "tv" under the "Add Download Client" menu.
<img width="500" alt="image" src="https://github.com/user-attachments/assets/b48577db-241d-48c6-912d-26e5edd0371f" />


  
Anytime you reference your media folder in a container you want the path to look like /share/media/tv instead of /tv like a lot of the default guides say, if you do end up mapping the path as /tv hardlinking will not work

## Possible Additions

1. Organizr - Creates a lovely dashboard to help navigate to all of your apps
2. Portainer - Docker GUI
3. UptimeKuma - Gives you the ability to monitor your services

