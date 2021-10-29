#About HydraPlay
HydraPlay is a multiroom audio server with web client which can control multiple Mopidy instances controlled by a Snapcast installation. Hydraplay consists of two
components. A server whichi written in Python. The server generates all the needed configs and starts all Mopidy and Snapcast instances.

HydraPlay was inspired by a project i have seen on [Youtube](https://www.youtube.com/watch?v=Lmr58F8gSs8&t=100s) by Ryan Detzel. 

*This project is still under development, some things might not work are unstable*

##Screenshots

<center>
<div float: center'>
  <img style="width: 400px" width="400px" src="doc/images/hydra.gif"></img>
</div>


<div float: center'>
  <img style="width: 200px" width="400px" src="doc/images/sc1.png"></img>
  <img style="width: 200px" width="400px" src="doc/images/sc4.png"></img>
</div>
</center>


## Getting Started

The easiest way to get it running is by using docker. Just checkout the source code from GitHub and change into the folder. Be sure that you have docker and docker-compose installed. Build the docker image by calling:

```
docker-compose build
```

Make a copy of the file `hydraplay.example.json` and rename it to `hydraplay.private.json`. This file will contain all you configurations for the setup. 

Open the file in an editor and make the changes you need. If you want to enable Spotify you will need a client_id and client_secret. Just follow the instructions of the [Mopidy Spotify extension](https://mopidy.com/ext/spotify/). Add the cliendId, client secret and your Spotify login credentials to the config. Set the enabled attribute in the config true.

Now you are able to start the server with:

```
docker-compose up
```

## Configuration
TODO

## Details 
You can find a [blog  post.](https://www.mariolukas.de/2019/07/hydraplay-open-source-multiroom-audio/) which i wrote a couple of years ago when i started the project. A lot of things changed since the first setup. But it will give you and idea on how it works under the hood.


### Known Issues
* mdns/avahi does not work within docker. You need to start your clients with  the -h <ip_address_of_server> parameter.

### Not Implemented yet

- [ ] remove track from tracklist
- [ ] change tracklist order
- [ ] save tracklist as playlist
- [ ] load playlists




