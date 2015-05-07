# Supported tags and respective `Dockerfile` links

-	[`14.04`](https://github.com/krmcbride/docker-ubuntu/blob/master/14.04/Dockerfile)

# What is Ubuntu?

Ubuntu is a Debian-based Linux operating system.  It is based on free software and named after 
the Southern African philosophy of ubuntu (literally, "human-ness"). Development of Ubuntu is 
led by UK-based Canonical Ltd. 

> [wikipedia.org/wiki/Ubuntu (Operating System)](http://en.wikipedia.org/wiki/Ubuntu_%28operating_system%29)

![logo](logo.png?raw=true)

# How to use this image

The base image extends the [official ubuntu image](https://registry.hub.docker.com/_/ubuntu/)
with usability enhancements, including bash aliases, a more informative colorized bash prompt,
and improved vim and git configuration.  It also creates a non-root `app` user and defines a
`/usr/src/app` volume.
