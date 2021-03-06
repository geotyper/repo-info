## `rethinkdb:latest`

```console
$ docker pull rethinkdb@sha256:d3317e44cbdae56fff64be2ac0096e5140987621d4b655641197cbd284071a8c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `rethinkdb:latest` - linux; amd64

```console
$ docker pull rethinkdb@sha256:d558dfd168983565c6dae01719c973528b4386e4fed49fc45aff0f0cbc43275f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **77.8 MB (77832015 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:49dd328850eb5c990a6d67aa1bb73131edc065154fd4b5f99445d246a0e72c36`
-	Default Command: `["rethinkdb","--bind","all"]`

```dockerfile
# Tue, 04 Sep 2018 21:19:53 GMT
ADD file:8d73a09e59fe50289a6d0c019302aefe2e00ac6411e82404389c0c83f50cf08a in / 
# Tue, 04 Sep 2018 21:19:54 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 05:29:56 GMT
MAINTAINER Daniel Alan Miller <dalanmiller@rethinkdb.com>
# Wed, 05 Sep 2018 05:30:03 GMT
RUN apt-key adv --keyserver keys.gnupg.net --recv-keys 3B87619DF812A63A8C1005C30742918E5C8DA04A
# Wed, 05 Sep 2018 05:30:04 GMT
RUN echo "deb http://download.rethinkdb.com/apt jessie main" > /etc/apt/sources.list.d/rethinkdb.list
# Wed, 05 Sep 2018 05:30:05 GMT
ENV RETHINKDB_PACKAGE_VERSION=2.3.6~0jessie
# Wed, 05 Sep 2018 05:30:32 GMT
RUN apt-get update 	&& apt-get install -y rethinkdb=$RETHINKDB_PACKAGE_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 05:30:33 GMT
VOLUME [/data]
# Wed, 05 Sep 2018 05:30:33 GMT
WORKDIR /data
# Wed, 05 Sep 2018 05:30:33 GMT
CMD ["rethinkdb" "--bind" "all"]
# Wed, 05 Sep 2018 05:30:33 GMT
EXPOSE 28015/tcp 29015/tcp 8080/tcp
```

-	Layers:
	-	`sha256:f189db1b88b3cab5fd17f74fee412610fe40d4b077e7882c1a50a8b6f4f0cea3`  
		Last Modified: Tue, 04 Sep 2018 21:23:11 GMT  
		Size: 54.3 MB (54252211 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b84ddae31889b847b9d0a2004b7be8cc3f910f72a6022a2601ca1944aab9122f`  
		Last Modified: Wed, 05 Sep 2018 05:30:46 GMT  
		Size: 4.1 KB (4112 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd04dc7a271823f637c79a35bf00c42c9ee7d788dfd482d315d3e7590a9a82ad`  
		Last Modified: Wed, 05 Sep 2018 05:30:45 GMT  
		Size: 214.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6914556605a20a9f7ad0d13f64569e52ea59ded4c47d38dc1e5a3ea0206e399`  
		Last Modified: Wed, 05 Sep 2018 05:30:50 GMT  
		Size: 23.6 MB (23575385 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0570462fb41181880d670ed7a52e3233c0bfc736199f55a63c5122d500cbc616`  
		Last Modified: Wed, 05 Sep 2018 05:30:46 GMT  
		Size: 93.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
