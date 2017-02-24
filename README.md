#### tvheadend-sundtek-docker

#### Notes
don't install Sundtek driver on your host.

#### Build
git clone {repository}
cd {repository}
docker build -t tvheadend/sundtek .

#### Run:
(only pass my dvbsky adapter to tvheadend not sundtek)
```bash
docker run \
--name="tvheadend" \
--link oscam:oscam \
--restart=always \
--privileged \
--net=bridge \
-v /media/8tb.wd.red/recordings/:/recordings \
-v /home/docker/tvheadend/:/config \
-v /home/docker/picons/:/picons \
-v /etc/localtime:/etc/localtime:ro \
-p 9981:9981 \
-p 9982:9982 \
--device=/dev/dvb/* \
-d tvheadend/sundtek
```

#### Picons:
https://github.com/picons/picons-source
