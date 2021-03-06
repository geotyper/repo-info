## `orientdb:latest`

```console
$ docker pull orientdb@sha256:2d5d49c84845681591bbc303d6c04417d916736ef5348fca8f0e17fca548da8e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:latest` - linux; amd64

```console
$ docker pull orientdb@sha256:b83f6576f6c02aca388a8cadc59cc26c9ed8ef1e332c4fda26716f179a0dfa07
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **110.0 MB (110000070 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4f812e2e2bd4b223558ccc2d5bf01a5b9c2d73895c3345ea1e697da72fd4c073`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 11 Sep 2018 22:19:50 GMT
ADD file:25c10b1d1b41d46a1827ad0b0d2389c24df6d31430005ff4e9a2d84ea23ebd42 in / 
# Tue, 11 Sep 2018 22:19:50 GMT
CMD ["/bin/sh"]
# Wed, 12 Sep 2018 00:06:51 GMT
ENV LANG=C.UTF-8
# Wed, 12 Sep 2018 00:06:51 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 12 Sep 2018 00:06:55 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 12 Sep 2018 00:06:55 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 12 Sep 2018 00:06:55 GMT
ENV JAVA_VERSION=8u171
# Wed, 12 Sep 2018 00:06:56 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 12 Sep 2018 00:06:59 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 12 Sep 2018 04:43:20 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 12 Sep 2018 04:43:37 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Wed, 12 Sep 2018 04:44:00 GMT
ENV ORIENTDB_VERSION=3.0.7
# Wed, 12 Sep 2018 04:44:00 GMT
ENV ORIENTDB_DOWNLOAD_MD5=abb35446395d652f0c0c9084b5d80550
# Wed, 12 Sep 2018 04:44:00 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=1fe8b333662495024ceabc712afac5e7a412f98a
# Wed, 12 Sep 2018 04:44:00 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/3.0.7/orientdb-community-3.0.7.tar.gz
# Wed, 12 Sep 2018 04:44:01 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Wed, 12 Sep 2018 04:44:04 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Wed, 12 Sep 2018 04:44:04 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 12 Sep 2018 04:44:04 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Wed, 12 Sep 2018 04:44:05 GMT
WORKDIR /orientdb
# Wed, 12 Sep 2018 04:44:05 GMT
EXPOSE 2424/tcp
# Wed, 12 Sep 2018 04:44:05 GMT
EXPOSE 2480/tcp
# Wed, 12 Sep 2018 04:44:05 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:4fe2ade4980c2dda4fc95858ebb981489baec8c1e4bd282ab1c3560be8ff9bde`  
		Last Modified: Tue, 11 Sep 2018 22:21:23 GMT  
		Size: 2.2 MB (2206931 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fc58a8d4ae4b3eeb215330632931dda9d60c645588c5750498ded35aa974c5a`  
		Last Modified: Wed, 12 Sep 2018 00:08:58 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe815adf554b18a057fade5a6b9498765d20c055f80d8d2facfb3a9cb00b66d0`  
		Last Modified: Wed, 12 Sep 2018 00:09:10 GMT  
		Size: 70.6 MB (70581326 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33b73d4940f53bd79a153bf646c71cb13b57c3280a9f465a8f8af968e190207c`  
		Last Modified: Wed, 12 Sep 2018 04:45:09 GMT  
		Size: 767.3 KB (767266 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e6d05eced8e6fc9c896aa6598543fb8c5c17c8a9ab47fa42bb37f0bb812ef4e`  
		Last Modified: Wed, 12 Sep 2018 04:45:13 GMT  
		Size: 36.4 MB (36444309 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
