## `neurodebian:wheezy`

```console
$ docker pull neurodebian@sha256:d9cc9cb32634c413e406f759da0f25f1f87d1d546179e0f24a1b21b8cc6e2f52
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `neurodebian:wheezy` - linux; amd64

```console
$ docker pull neurodebian@sha256:3251058b07e9a5b29a91cf0991496bdd3f3ad42c73e38116fa6240290a436eda
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **39.3 MB (39343336 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:565790f39cca3164d7ccb38e5f75002972e2233efc1bc00921c60ef6eb1cf60e`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 04 Sep 2018 21:22:11 GMT
ADD file:1d0d47b9e887adff2328eeb380e2cc47982a572942a29d7ed26bcf6291219302 in / 
# Tue, 04 Sep 2018 21:22:11 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 00:45:09 GMT
RUN set -x 	&& apt-get update 	&& { 		which gpg 		|| apt-get install -y --no-install-recommends gnupg 	; } 	&& { 		gpg --version | grep -q '^gpg (GnuPG) 1\.' 		|| apt-get install -y --no-install-recommends dirmngr 	; } 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 00:45:09 GMT
RUN set -x 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys DD95CC430502E37EF840ACEEA5D32F012649A5A9 	&& gpg --export DD95CC430502E37EF840ACEEA5D32F012649A5A9 > /etc/apt/trusted.gpg.d/neurodebian.gpg 	&& rm -rf "$GNUPGHOME" 	&& apt-key list | grep neurodebian
# Wed, 05 Sep 2018 00:45:10 GMT
RUN { 	echo 'deb http://neuro.debian.net/debian wheezy main'; 	echo 'deb http://neuro.debian.net/debian data main'; 	echo '#deb-src http://neuro.debian.net/debian-devel wheezy main'; } > /etc/apt/sources.list.d/neurodebian.sources.list
```

-	Layers:
	-	`sha256:703d6f3fb41c45d33d1e6358aba66a774c9ebc11a21bc5dfef74f20d043d3933`  
		Last Modified: Tue, 04 Sep 2018 21:26:45 GMT  
		Size: 39.3 MB (39339633 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa81e04d5130fba91d21306aa8cbd8dc4a185b333e713cd92a6afb846c08d9ad`  
		Last Modified: Wed, 05 Sep 2018 00:48:02 GMT  
		Size: 276.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ffedbc42a89fb477fcf25ca98ee544d749d83454378fcda31e1a2d3c71b6f86`  
		Last Modified: Wed, 05 Sep 2018 00:48:02 GMT  
		Size: 3.2 KB (3186 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:deb923cf547ec53a44bc9ba0fbf0562432013cc2f4f4d810fc218514f564da74`  
		Last Modified: Wed, 05 Sep 2018 00:48:02 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
