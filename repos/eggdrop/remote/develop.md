## `eggdrop:develop`

```console
$ docker pull eggdrop@sha256:b6f3edff6d93dc29cd5b780c8370bd94a4f691d21f62e4b58b346b947c51f539
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `eggdrop:develop` - linux; amd64

```console
$ docker pull eggdrop@sha256:5f3c52fcf56ad81a2e93297e5d086358557ac6db264777c832f152f919a7c962
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.8 MB (13845644 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b569b2cbf105a5cbc43feaa042e2f43a1480e9a31e669d037ab0755b66b6ec1f`
-	Entrypoint: `["\/home\/eggdrop\/eggdrop\/entrypoint.sh"]`
-	Default Command: `["eggdrop.conf"]`

```dockerfile
# Tue, 11 Sep 2018 22:19:38 GMT
ADD file:49f9e47e678d868d5b023482aa8dded71276a241a665c4f8b55ca77269321b34 in / 
# Tue, 11 Sep 2018 22:19:39 GMT
CMD ["/bin/sh"]
# Tue, 11 Sep 2018 22:53:24 GMT
MAINTAINER Geo Van O <geo@eggheads.org>
# Tue, 11 Sep 2018 22:53:25 GMT
RUN adduser -S eggdrop
# Tue, 11 Sep 2018 22:53:26 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Mon, 17 Sep 2018 20:21:13 GMT
ENV EGGDROP_SHA256=74212f33f8c44be68ea6bd8c41f636620771328f9e8dc1549e218e637efbc9bc
# Mon, 17 Sep 2018 20:21:13 GMT
ENV EGGDROP_COMMIT=83d237a1d82a74dd36c86bacd4b833131143c062
# Mon, 17 Sep 2018 20:21:15 GMT
RUN apk --update add --no-cache tcl bash openssl
# Mon, 17 Sep 2018 20:22:11 GMT
RUN apk --update add --no-cache --virtual egg-deps tcl-dev wget ca-certificates make tar gpgme build-base openssl-dev   && wget "https://github.com/eggheads/eggdrop/archive/$EGGDROP_COMMIT.tar.gz" -O develop.tar.gz   && echo "$EGGDROP_SHA256  develop.tar.gz" | sha256sum -c -   && tar -zxvf develop.tar.gz   && rm develop.tar.gz     && ( cd eggdrop-$EGGDROP_COMMIT     && ./configure     && make config     && make     && make install DEST=/home/eggdrop/eggdrop )   && rm -rf eggdrop-$EGGDROP_COMMIT   && mkdir /home/eggdrop/eggdrop/data   && chown -R eggdrop /home/eggdrop/eggdrop   && apk del egg-deps
# Mon, 17 Sep 2018 20:22:15 GMT
ENV NICK=
# Mon, 17 Sep 2018 20:22:15 GMT
ENV SERVER=
# Mon, 17 Sep 2018 20:22:15 GMT
ENV LISTEN=3333
# Mon, 17 Sep 2018 20:22:15 GMT
ENV OWNER=
# Mon, 17 Sep 2018 20:22:16 GMT
ENV USERFILE=eggdrop.user
# Mon, 17 Sep 2018 20:22:16 GMT
ENV CHANFILE=eggdrop.chan
# Mon, 17 Sep 2018 20:22:16 GMT
WORKDIR /home/eggdrop/eggdrop
# Mon, 17 Sep 2018 20:22:16 GMT
EXPOSE 3333/tcp
# Mon, 17 Sep 2018 20:22:17 GMT
COPY file:d80744926cf822928c4fc2c3f9107364df320eecb3ae407a3a5419a43ae4b872 in /home/eggdrop/eggdrop 
# Mon, 17 Sep 2018 20:22:17 GMT
COPY file:919804e5ddd4c807c178caccfed03e9d75a459fe0f744c3a1ada109817cb44ec in /home/eggdrop/eggdrop/scripts/ 
# Mon, 17 Sep 2018 20:22:17 GMT
ENTRYPOINT ["/home/eggdrop/eggdrop/entrypoint.sh"]
# Mon, 17 Sep 2018 20:22:17 GMT
CMD ["eggdrop.conf"]
```

-	Layers:
	-	`sha256:c67f3896b22c1378881cbbb9c9d1edfe881fd07f713371835ef46d93c649684d`  
		Last Modified: Tue, 11 Sep 2018 22:21:16 GMT  
		Size: 2.1 MB (2107175 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:926d70e02e336bd99f571b4dcb3559e271e8828692d98358bbe5356307e1a53e`  
		Last Modified: Tue, 11 Sep 2018 22:56:19 GMT  
		Size: 1.3 KB (1257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce023cda4d8be9e674bd3470ea36deef2f550e397afa48daac7dba6486e38b49`  
		Last Modified: Tue, 11 Sep 2018 22:56:18 GMT  
		Size: 8.8 KB (8847 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55cd11474fbfd9e854fad6684f6ca60a73b9f7a5f6fe7307f6322dc6ecb32fbc`  
		Last Modified: Mon, 17 Sep 2018 20:22:43 GMT  
		Size: 4.4 MB (4402025 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66c7b7598e1304a13c69ec71646bdac48eb75420929d8c5511065475d9f6e808`  
		Last Modified: Mon, 17 Sep 2018 20:22:44 GMT  
		Size: 7.3 MB (7323747 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6efd53f0a731fd38b15662eb35307e89aa9d0b7a70118b696d7cafebacc673cd`  
		Last Modified: Mon, 17 Sep 2018 20:22:42 GMT  
		Size: 1.9 KB (1885 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71788901a3240b2d442e017fa44f891aeeac71e263646899002ff14674d8afda`  
		Last Modified: Mon, 17 Sep 2018 20:22:42 GMT  
		Size: 708.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
