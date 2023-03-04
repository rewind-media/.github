## Welcome
Rewind is a set of components making up a self-hosted media server akin to [Jellyfin](https://jellyfin.org/) or [Plex](https://www.plex.tv/). However, Rewind supports high available deployments, and is designed to be modular, scalable, and highly customizable.

Rewind is currently in __Alpha__ state, meaning that breaking changes, especially to data models, are likely to be made with no migration plans provided. A current state of functionality:
* Series (TV Shows) in [Sonarr Standard Series Heirarchy](https://wiki.servarr.com/sonarr/settings)
* OpenApi spec with Kotlin (Android) and TypeScript client generation
* Proof-of-concept, functional Android app
* On-demand HLS streams working in Browser and Android
* Redis and MongoDB cache and database interfaces written
* Core containers published and useable with docker-compose

## Components
| Component     | Notes                                                                                | Dependencies                               |
|---------------|--------------------------------------------------------------------------------------|--------------------------------------------|
| rewind-api    | Public API that also serves up the React web client                                  | rewind-web, rewind-common, rewind-protocol |
| rewind-cron   | Singleton timer for handling synchronization and other non-critical tasks            | rewind-common, rewind-protocol             |
| rewind-worker | On-demand transcoder responsible for file access and processing on behalf of the API | rewind-common, rewind-protocol             |


