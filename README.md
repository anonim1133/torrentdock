Docker for rtorrent + ruTorrent(web ui)


# Installation:
```
git clone https://github.com/anonim1133/torrentdock.git
cd torrentdock
git clone https://github.com/Novik/ruTorrent.git
```
# Configuration
Everything is set just barely to work.
In nginx you can change your domain, or turn off autorization with HTTP AUTH
    - **You should generate** new htapasswd entry and put it in file (there are online generators that works just fine)

In rtorrent config do not touch the top part, as it's quite crucial to run it.
    - Downloaded files are kept in rtorrent/downloads

ruTorrent is available at :2138 port - it is possible to change it in dockercompose.

Now **you should** fix these lines in rutorrent config, as I was too lazy to make it automagically.

```
$scgi_port = 5000;
$scgi_host = "rtorrent";

$localhosts = array( 			// list of local interfaces
    "127.0.0.1",
    "localhost",
    "rtorrent",
)
```

**docker-compose build** to build imagess, and **docker-compose up -d** to run it (in background, becouse of "-d").