## Installation

- set variables

```sh
export ONEDRIVE_CONFIG_DIR=~/.config/onedrive/
export ONEDRIVE_DIR=~/.config/onedrive/
```

- initialize with `docker-compose run onedrive gosu onedrive /usr/local/bin/onedrive --verbose --monitor --confdir /onedrive/conf --syncdir /onedrive/data` and follow the steps described

## Add sync to shared folders

First log into running container:
`docker-compose exec onedrive gosu onedrive bash`

Then execute according to the documentation to see all shared drives:
`docker-compose run onedrive gosu onedrive /usr/local/bin/onedrive --confdir /onedrive/conf --syncdir /onedrive/data --list-shared-folders`

To add a shared drive, create/update the following config file
`vi ~/.config/onedrive/business_shared_folders`

and provide content like:

```
# Server Share of Ebooks
7-Literatur
```

After that, start the sync process again
`docker-compose run onedrive gosu onedrive /usr/local/bin/onedrive --confdir /onedrive/conf --syncdir /onedrive/data --synchronize --sync-shared-folders`
