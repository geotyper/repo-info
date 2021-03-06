## `debian:rc-buggy`

```console
$ docker pull debian@sha256:8cd438cf1474d82bbfd14d53ef2a431b83a217d13fe91ed1c2fb50c09133cca8
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `debian:rc-buggy` - linux; amd64

```console
$ docker pull debian@sha256:9db87a741d89ad6694eefefcfcb9404e89a2cfde26be5a669fbd9c94ab062d69
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **49.1 MB (49071931 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1e163c2cb4f38bf05a9239d74a0b3f0cf0a4f20d578e48651825a0ce77c196f6`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 04 Sep 2018 21:20:51 GMT
ADD file:6b6ece05e75fbdccfdd76433844e066f0ec636fb62e74326f1747ccde948c381 in / 
# Tue, 04 Sep 2018 21:20:52 GMT
CMD ["bash"]
# Tue, 04 Sep 2018 21:22:29 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:5164339600396c4bdb97f111e5236c5fc64911bbd2bfe6d2343ce45fe79ea7d8`  
		Last Modified: Tue, 04 Sep 2018 21:24:41 GMT  
		Size: 49.1 MB (49071704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:180f74821ec1eb51761b0a9ef9d7944c3757de7dbb4665e8759aaee81cf8fed5`  
		Last Modified: Tue, 04 Sep 2018 21:27:12 GMT  
		Size: 227.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; arm variant v5

```console
$ docker pull debian@sha256:86322e82dfca71113c8002c931dc29197edf93c27c8414669247e51e931c4141
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **46.8 MB (46817327 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b7680a5f15307d0c0bf4e884854e8d8b6f99ec364013b853dee93e0b6a4dadab`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 05 Sep 2018 08:53:05 GMT
ADD file:197405a6e437f7755c9e1eaaeffa366cbbed5d22b6433e8985fc72c0399c9741 in / 
# Wed, 05 Sep 2018 08:53:10 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 08:57:55 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:d249ae748c1383631885fe6ef102c9f4763c974c7e2ed31cbd7b8ec3b469b01e`  
		Last Modified: Wed, 05 Sep 2018 09:02:23 GMT  
		Size: 46.8 MB (46817101 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8024bc1ae8346d339e7ab90ea0c58d1e74ba7a6416ba60c4ceca08d8d5b7397`  
		Last Modified: Wed, 05 Sep 2018 09:07:54 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; arm variant v7

```console
$ docker pull debian@sha256:a6d0fda9bbdb38da8a91ecd384ccd895fc6b386abbd742df241542a9e2346fb9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **44.7 MB (44660706 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:22c7379af9efc50f3b9a542545de4e243dc60834f509fa4eebf8aa77b8942403`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 05 Sep 2018 12:02:03 GMT
ADD file:6bce3a6eaae154a74bd434bc6087c35774f3ca30b31179bd9d3a8ccc883e6356 in / 
# Wed, 05 Sep 2018 12:02:08 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 12:07:09 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:41ac34bbb663ff9b66612cbe07ba88955dbe37f15f0732d7438ed9d75ffef0c9`  
		Last Modified: Wed, 05 Sep 2018 12:11:20 GMT  
		Size: 44.7 MB (44660481 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8d4c3998a7bb795a89dc50542873c226b681b1f95d2d03073f53b1e057cb0b8`  
		Last Modified: Wed, 05 Sep 2018 12:16:50 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; arm64 variant v8

```console
$ docker pull debian@sha256:eb25de72616ca351ba64a3250ce1c164d0324dd0d81a9b3fd91c7607b19af6f3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **47.2 MB (47246433 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cc16e2856e9606afafe239312b9aedb1ee69c94acae18ec9a2a24b308aebb6e8`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 05 Sep 2018 08:44:44 GMT
ADD file:cac51be1621603e67cd0c6a08ff297ca705beef482ba784194fe06790776dda8 in / 
# Wed, 05 Sep 2018 08:44:45 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 08:59:07 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:ff5ead7611ad86204643cd46d308599be45fefaca7a358aa65ccab791156f31f`  
		Last Modified: Wed, 05 Sep 2018 09:02:06 GMT  
		Size: 47.2 MB (47246205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e71ecf769ff0381c275fc80dc388971554be7c0d1e067452e2f3cd160417407`  
		Last Modified: Wed, 05 Sep 2018 09:15:28 GMT  
		Size: 228.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; 386

```console
$ docker pull debian@sha256:e9f771455e05831fb7e8eb1051f886de95e876eb90bd723db855fedb312fe544
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **49.8 MB (49764721 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f0e5e11e1558cc18fa2c11b2ca4f4ae1dd3911820716fa4d9cb70af51ebf6e6b`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 05 Sep 2018 10:42:05 GMT
ADD file:8de67e0fc0d437844f80c43c2040a020c9b920f19c3af0645d06ad1f79099fd9 in / 
# Wed, 05 Sep 2018 10:42:06 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 10:46:22 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:c5ab6b8677b80e3d03b9cf7f6d60c5ea5e55c3ef5201228d2a1e02348632bc3b`  
		Last Modified: Wed, 05 Sep 2018 10:50:26 GMT  
		Size: 49.8 MB (49764498 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2180a91bc8100893357d8a1c1518342a5b7d9054cd9ca2d6e58f863be2fcdfb`  
		Last Modified: Wed, 05 Sep 2018 10:54:39 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; ppc64le

```console
$ docker pull debian@sha256:49fdeae4a20639b96954a99ac5c84196417be5ec479ee19692d6192b040e947b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **51.8 MB (51844159 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fd5588956a02a908c2f80f49313f2ccc4d09c23fbe999dd3d9aee817d3bc5cd4`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 05 Sep 2018 08:17:51 GMT
ADD file:74cafd19c9f92f0bcf0ebf8af7c5fab91202cd413254da05d5a2b9191ecbee2d in / 
# Wed, 05 Sep 2018 08:17:53 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 08:21:37 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:88839b4f566005ace21b4fb23e56b4a9638df137ee204c622d554444045423e4`  
		Last Modified: Wed, 05 Sep 2018 08:23:23 GMT  
		Size: 51.8 MB (51843930 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c13f8c0137442484dc1c07769339e85a4253300b3416b6fff6497c8df362a1b2`  
		Last Modified: Wed, 05 Sep 2018 08:29:27 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; s390x

```console
$ docker pull debian@sha256:9fb9d9fcbeccaaeda670825bb8b451f22b8f165fea1720187f6708ab25ad7924
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **47.7 MB (47670652 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8ba40cca21c0afe0efea840e4b9eeddedb543392433df80ef6668d17722fc035`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 05 Sep 2018 11:42:29 GMT
ADD file:832b68a7f8033560aa3536d9163f28d197490633c05d49240dd2bed266d9504e in / 
# Wed, 05 Sep 2018 11:42:30 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 11:46:15 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:b9886f96c1f9394ba76a75262b09bb6ad6b8100a8d94cf87089d43cb2068efe3`  
		Last Modified: Wed, 05 Sep 2018 11:47:17 GMT  
		Size: 47.7 MB (47670424 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ff8144e5854bdbaac3534f4a0d56538298f94b98a3c01fba0c6a5d20c7be6fe`  
		Last Modified: Wed, 05 Sep 2018 11:51:01 GMT  
		Size: 228.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
