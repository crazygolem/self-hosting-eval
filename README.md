
I started this project to evaluate several self-hosting file-sharing solutions
for my personal needs.

I wanted to try those solutions out locally using docker containers with podman.
This proved a tad challenging in some cases as most solutions that do support
docker containers have example for docker and docker-compose. This needed a few
adaptations to work with podman.

I tried to use podman-compose but could not make it work (probably some very
basic PEBCAK issue) but since it was the first time using podman I quickly
dropped podman-compose to get some hands on experience with podman itself.

The result are a few bash script that run podman commands to set up the self-
hosting solutions. It's not too pretty. AND IT'S CERTAINLY NOT FOR PRODUCTION.


# Resources

A lot of self-hosting stuff in all kinds of categories:
* https://github.com/awesome-selfhosted/awesome-selfhosted
* https://github.com/awesome-selfhosted/awesome-selfhosted/blob/master/non-free.md


# Evaluations

For my purpose I wanted something that's good looking and intuitive in the
domain of file sharing.

This is what matters to me:

* Good-looking, modern and intuitive GUI. Should allow drag-n-dropping files
  from my desktop's file manager.
* Can create several public share links with their own configuration (e.g.
  permissions, expiration)
* Allows downloading an entire directory and its subdirectories at once
* A music player that allows to play all the music files in a directory
* It should allow the use of an external data sync mechanism
* A libre license


## All-in-one solutions

### NextCloud

Self-hosting solution
https://nextcloud.com

* (+) Overall good UI (4*)
* (+) Can create multiple share links with own config (e.g. expiration)
* (+) Audio player ("Music", not "Audio Player") is OK. Good integration with the
  file browser, keeps playing while browsing other directories.
* (~) 3rd-party sync is possible using the "External storage support" plugin, but it
  is not integrated with the internal file hierarchy.

### FileRun

Web-based file browser with some extras

https://filerun.com

* (+) Very polished UI (5*)
* (+) Nice audio player
* (+) Integrates with any file-syncing backend (e.g. SyncThing)
* (-) Free version limited to 3 users (or 10 after contacting company)
* (-) Not open source
* (-) Only a single share link possible

### Pydio Cells

File sharing platform

https://pydio.com

* (+) Good, Clean UI (4*)
* (~) Integrates with any file-syncing backend, but requires some extra
  scripting to sync the datasource on changes
* (-) Audio player not good, very basic
* (-) Only a single share link possible

### Seafile

File sync and sharing platform

https://www.seafile.com

* (~) Clean UI (3*), drag-n-drop not supported
* (-) Only a single share link possible
* (-) File-by-file audio player
* (-) Not meant to be integrated with a file-syncing backend

### Cozy

Personal data management platform

https://github.com/cozy/cozy-stack

Review is for the file-management app (drive)

* (+) Clean UI (4*), with some bugs (e.g. menu not entirely visible)
* (-) Not meant to integrate with a file-syncing backend
* (-) Only a single share link possible (maybe extra links if sent by email?)
* (-) Basic file-by-file browser-native player

### ownCloud

Similar to nextcloud, with a UI a bit less polished.

https://owncloud.com

* (~) Overall okay UI, less nice than nextcloud (2*)
* (-) Only a single share link possible
* (-) Audio player is not very good


## Separate applications

Extra requirements to integrate separate applications nicely:
* Allow external accounts management (e.g. SSO) or at least disable
  authentication entirely with minimal loss of features.

Some resources:
* https://thehomelab.wiki/books/docker/page/deemix-navidrome-and-filebrowser---the-ultimate-music-docker-stack

### File Browser

Web-based file browser

https://github.com/filebrowser/filebrowser

* (+) Good UI (4*), no right-click app-menu
* (+) Integrates with any file-syncing backend
* (-) Only a single permanent share link, but it is possible to create
      additional share links that expire.
* (-) Can only limit user access to a single directory (called "scope"), not
      possible to add extra shared directories outside of that "scope".
* (-) Possibility to disable authentication entirely, but not use external
      accounts management.


### Navidrome

Music player which implements standard remote play protocols

https://github.com/deluan/navidrome

* (+) Good UI (4*)
* (+) Integrates with any file-syncing backend
* (+) Remote streaming with on-the-fly transcoding
* (+) Can import automatically external playlists (m3u)
* (-) No directory-based browsing
* (-) Cannot use external accounts management nor disable authentication


## TODO

### Filestash

https://github.com/mickael-kerjean/filestash

TODO


## Mentions

* KodExplorer: Virtual Desktop in a Browser (out of scope)

  https://github.com/kalcaddle/KodExplorer
