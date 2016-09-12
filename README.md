flexget-fedora
==============
[![](https://images.microbadger.com/badges/image/eminguez/flexget-fedora.svg)](https://microbadger.com/images/eminguez/flexget-fedora "Get your own image badge on microbadger.com")

Flexget Docker Container based in Fedora

Application container, the idea is to run it from cron (or better, incron) to parse your transmission download folder to your tv shows library:

```
docker run --rm --name flexget \
  --net=container:transmission \
  -v /local/dir/config/:/home/flexget/.config/flexget/ \
  -v /local/dir/downloads:/home/flexget/flexget/from \
  -v /local/dir/media/tvshows:/home/flexget/flexget/to \
  eminguez/flexget-fedora
```

It runs in the same network namespace as the transmission one (using ```--net=container:transmission```), so it can connect to "localhost" to feed transmission

A sample config file can be found in config.yml.sample
