# Docker popcorns

This is a first implementation of a docker-composer environment to raise a pipeline of SickRage, Plex and Transmission.

# Software Requirements

* [Docker](https://docs.docker.com/installation/#installation)
* [Docker-compose](https://docs.docker.com/compose/)

# Setup

* Fetch latest archive and unpack it somewhere.
* sudo mkdir /srv/popcorns/sickrage-config /srv/popcorns/sickrage-data /srv/popcorns/downloads /srv/popcorns/tv /srv/popcorns/plex-library /srv/popcorns/downloads
* sudo chmod 777 /srv/popcorns/*
* docker-compose up

### SickRage

* Access to http://localhost:8081.
* [Configure Torrent search](http://localhost:8081/config/search/): enable transmission, url http://localhost:9091, user admin, password admin.
* [Configure search providers](http://localhost:8081/config/providers)
* [Configure post-processing](http://localhost:8081/config/postProcessing/) set *tv download dir* to **/downloads**, enable *Scan and Process*.
* [Add a new show](http://localhost:8081/home/addShows/newShow/), set **/tv** as *parent folder*.

### Transmission

* Access to http://localhost:9091, user admin, pass admin.

### Plex

* Access to http://localhost:32400/web/index.html, add **/tv** as TV series folder
