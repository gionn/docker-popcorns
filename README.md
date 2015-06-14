# Docker popcorns

This is a first implementation of a docker-composer environment to raise a pipeline of SickRage, Plex and Transmission.

# Software Requirements

* [Docker](https://docs.docker.com/installation/#installation)
* [Docker-compose](https://docs.docker.com/compose/)

# Setup

* Fetch [latest archive](https://github.com/gionn/docker-popcorns/archive/master.zip) and unpack it somewhere.
* Create persistent data folders:
```
sudo mkdir /srv/popcorns/{sickrage-config,sickrage-data,downloads,tv,plex-library,downloads}
```

* Give permissions (we don't care):
```
sudo chmod 777 /srv/popcorns/*
```

* docker-compose up

### SickRage

* Access to [http://localhost:8081](http://localhost:8081).
* [Configure Torrent search](http://localhost:8081/config/search/): enable transmission intgration, set *url* **http://localhost:9091**, user *admin*, password *admin*.
* [Configure search providers](http://localhost:8081/config/providers), enable some of them (note: some requires user/password).
* [Configure post-processing](http://localhost:8081/config/postProcessing/) set *tv download dir* to **/downloads**, enable *Scan and Process*.
* [Add a new show](http://localhost:8081/home/addShows/newShow/), set **/tv** as *parent folder*.

### Transmission

* Access to [http://localhost:9091](http://localhost:9091), user admin, pass admin.

### Plex

* Access to [http://localhost:32400/web/index.html](http://localhost:32400/web/index.html), add **/tv** as TV series folder
