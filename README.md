norikra-alpine
===

[Norikra](http://norikra.github.io) on [Alpine Linux](https://alpinelinux.org/) (with [JRuby](http://jruby.org/) 9k)

```sh
docker run -d \
         -p 26578:26578 -p 26571:26571 \ # For norikra
         -p 8778:8778 \ # For jolokia
         -v /var/tmp/norikra:/var/tmp/norikra:rw \
         -t hfmgarden/norikra-alpine \
         norikra start -Xmx2g -javaagent:/opt/jolokia/jolokia-jvm-agent.jar=port=8778,host=0.0.0.0,discoveryEnabled=false --stats /var/tmp/norikra/stats.json -l /var/tmp/norikra
```
