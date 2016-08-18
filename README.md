# BitlBee rpi-docker image (ARM)

## Description


BitlBee brings IM (instant messaging) to IRC clients. It's a great solution for
people who have an IRC client running all the time and don't want to run an
additional MSN/AIM/whatever client.

This image allows you to run BitlBee in a completelly containerized environment

## How to use this image

Run BitlBee listening in port 6667 with default config
```
docker run \
  -p 6667:6667 \
  plod/docker-rpi-bitlbee -n
```

Use a specific config directory
```
docker run \
  -p 6667:6667 \
  -v $(pwd)/bitlbee:/etc/bitlbee:ro \
  fr3nd/bitlbee -n
```

Store all data into a parent host's directory
```
docker run \
  -p 6667:6667 \
  -v /tmp/bitlbee:/var/lib/bitlbee:rw \
  plod/docker-rpi-bitlbee -n
```
