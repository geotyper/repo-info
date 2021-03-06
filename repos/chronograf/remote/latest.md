## `chronograf:latest`

```console
$ docker pull chronograf@sha256:e3549df85bb0914981ee77a6ec1c1dd9e085f796f671330fa9319ac4945cbf9f
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8

### `chronograf:latest` - linux; amd64

```console
$ docker pull chronograf@sha256:30c7a3a1fae5e45aa28ff5d5f326eca11aa81d39c5c17ffbd309bc7a307785d3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **49.1 MB (49088755 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:48fd0a33f7bf2537a5c01e9adde19f707d0b474301e8c6eea4dcc621300b1646`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["chronograf"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:34 GMT
ADD file:e6ca98733431f75e97eb09758ba64065d213d51bd2070a95cf15f2ff5adccfc4 in / 
# Tue, 04 Sep 2018 21:21:34 GMT
CMD ["bash"]
# Tue, 04 Sep 2018 23:04:19 GMT
RUN set -ex &&     apt-get update && apt-get install -y gpg dirmngr --no-install-recommends &&     rm -rf /var/lib/apt/lists/* &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Fri, 07 Sep 2018 18:19:37 GMT
ENV CHRONOGRAF_VERSION=1.6.2
# Fri, 07 Sep 2018 18:20:57 GMT
RUN ARCH= && dpkgArch="$(dpkg --print-architecture)" &&     case "${dpkgArch##*-}" in       amd64) ARCH='amd64';;       arm64) ARCH='arm64';;       armhf) ARCH='armhf';;       armel) ARCH='armel';;       *)     echo "Unsupported architecture: ${dpkgArch}"; exit 1;;     esac &&     set -x &&     apt-get update && apt-get install -y ca-certificates curl --no-install-recommends &&     rm -rf /var/lib/apt/lists/* &&     curl -SLO "https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb.asc" &&     curl -SLO "https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb" &&     gpg --batch --verify chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb.asc chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb &&     dpkg -i chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb &&     rm -f chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb* &&     apt-get purge -y --auto-remove $buildDeps
# Fri, 07 Sep 2018 18:20:58 GMT
COPY file:30de17380b1f353617f3efd8df8d07d842ebdd75d750781b20cc7588a54c918d in /usr/share/chronograf/LICENSE 
# Fri, 07 Sep 2018 18:20:58 GMT
COPY file:8cfc239e035af78ba9337d25f99200091e0d054985fe0c87e60b767d7759d99d in /usr/share/chronograf/agpl-3.0.md 
# Fri, 07 Sep 2018 18:20:58 GMT
EXPOSE 8888/tcp
# Fri, 07 Sep 2018 18:20:58 GMT
VOLUME [/var/lib/chronograf]
# Fri, 07 Sep 2018 18:20:59 GMT
COPY file:5e829c8058b054261083c78e0bc7ad8730ab2331be79c5c3e1b6b84993b3224b in /entrypoint.sh 
# Fri, 07 Sep 2018 18:20:59 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Fri, 07 Sep 2018 18:20:59 GMT
CMD ["chronograf"]
```

-	Layers:
	-	`sha256:802b00ed6f79f48e6a5f44ecbcaf43563d6077aaecb565eee1dfc615c0b18c00`  
		Last Modified: Tue, 04 Sep 2018 21:25:45 GMT  
		Size: 22.5 MB (22485965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ded6d78d8b9128ef2922f65a07020a45fcce2e51f020676fb77f45f5f6894dc`  
		Last Modified: Tue, 04 Sep 2018 23:05:28 GMT  
		Size: 4.5 MB (4500369 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ef6986b56db9c58b16200e766e424d07314e0bdafc3bb89048c8308587a506c`  
		Last Modified: Fri, 07 Sep 2018 18:21:33 GMT  
		Size: 22.1 MB (22078024 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6a8daa839b494a8263bb0c2ae05c814d9a8bab4bb7751fe2c3cdffac61fa491`  
		Last Modified: Fri, 07 Sep 2018 18:21:29 GMT  
		Size: 12.2 KB (12249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1be6a7978d949b0fbba691c4cba8dc4c51426939a317799b3d6ba422b7a8526f`  
		Last Modified: Fri, 07 Sep 2018 18:21:28 GMT  
		Size: 11.9 KB (11908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed12a14c4ba522152ae52b7c52f9ac1f1db5da2d918484776beae38ff2423185`  
		Last Modified: Fri, 07 Sep 2018 18:21:28 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `chronograf:latest` - linux; arm variant v7

```console
$ docker pull chronograf@sha256:91da97c34bf6acf0cc8c92ad6fd155ec060980b5dd9a4c05707772c7f5addaa2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **43.7 MB (43672306 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ae26070333dfa6f31af5d45f882bbd93a96d183d86924252dddc1bd5009398f9`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["chronograf"]`

```dockerfile
# Wed, 05 Sep 2018 12:04:38 GMT
ADD file:d20313e46e6d5f092327691d5bc0e83ad6b16d7b44a8dc82fa973c25a13257e7 in / 
# Wed, 05 Sep 2018 12:04:38 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 12:32:39 GMT
RUN set -ex &&     apt-get update && apt-get install -y gpg dirmngr --no-install-recommends &&     rm -rf /var/lib/apt/lists/* &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Sat, 08 Sep 2018 11:58:26 GMT
ENV CHRONOGRAF_VERSION=1.6.2
# Sat, 08 Sep 2018 11:58:47 GMT
RUN ARCH= && dpkgArch="$(dpkg --print-architecture)" &&     case "${dpkgArch##*-}" in       amd64) ARCH='amd64';;       arm64) ARCH='arm64';;       armhf) ARCH='armhf';;       armel) ARCH='armel';;       *)     echo "Unsupported architecture: ${dpkgArch}"; exit 1;;     esac &&     set -x &&     apt-get update && apt-get install -y ca-certificates curl --no-install-recommends &&     rm -rf /var/lib/apt/lists/* &&     curl -SLO "https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb.asc" &&     curl -SLO "https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb" &&     gpg --batch --verify chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb.asc chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb &&     dpkg -i chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb &&     rm -f chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb* &&     apt-get purge -y --auto-remove $buildDeps
# Sat, 08 Sep 2018 11:58:47 GMT
COPY file:30de17380b1f353617f3efd8df8d07d842ebdd75d750781b20cc7588a54c918d in /usr/share/chronograf/LICENSE 
# Sat, 08 Sep 2018 11:58:48 GMT
COPY file:8cfc239e035af78ba9337d25f99200091e0d054985fe0c87e60b767d7759d99d in /usr/share/chronograf/agpl-3.0.md 
# Sat, 08 Sep 2018 11:58:48 GMT
EXPOSE 8888/tcp
# Sat, 08 Sep 2018 11:58:49 GMT
VOLUME [/var/lib/chronograf]
# Sat, 08 Sep 2018 11:58:51 GMT
COPY file:5e829c8058b054261083c78e0bc7ad8730ab2331be79c5c3e1b6b84993b3224b in /entrypoint.sh 
# Sat, 08 Sep 2018 11:58:51 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 08 Sep 2018 11:58:51 GMT
CMD ["chronograf"]
```

-	Layers:
	-	`sha256:2e5bbd238113a2057012dfb78ac9665531c276c48962d208492c8802fb0503c0`  
		Last Modified: Wed, 05 Sep 2018 12:13:41 GMT  
		Size: 19.3 MB (19270166 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:83495d4601b2e67bb7dac70ca9e7b3b854c45aea2a30d4332d7caaf662cdc14e`  
		Last Modified: Wed, 05 Sep 2018 12:33:58 GMT  
		Size: 3.9 MB (3873190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6824db1649b9c884e93ac65b076ce58e3ef6824bdc6d157d5a5f3dad16d72b4`  
		Last Modified: Sat, 08 Sep 2018 11:59:20 GMT  
		Size: 20.5 MB (20504558 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9390ab66bc0bc364e32ea2e4df5815d8c10e9981d2341014edec592e307c9b05`  
		Last Modified: Sat, 08 Sep 2018 11:59:13 GMT  
		Size: 12.2 KB (12248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa8d3c3169c003435aae64027e00117bd831acee3797052d9037272aa09fce98`  
		Last Modified: Sat, 08 Sep 2018 11:59:13 GMT  
		Size: 11.9 KB (11904 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90e37e206ed4fd972aaef472cadc1296c8a12aa0b4b2c45118003ae590f1663a`  
		Last Modified: Sat, 08 Sep 2018 11:59:13 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `chronograf:latest` - linux; arm64 variant v8

```console
$ docker pull chronograf@sha256:6ed338d7fb62aaacd9f727bdb96145fe49aaae5322b3b3fec50a9374e98c9944
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **45.1 MB (45132406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3ad7ee32b24ac7d4d53e7ee3c7a661545efba34bccfce88ffa1b30eb0a30d6f5`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["chronograf"]`

```dockerfile
# Wed, 05 Sep 2018 08:51:48 GMT
ADD file:11982f247d3c0dc005ade5290cf65e3e0f9d4a64f141d4d63317af8680ef094a in / 
# Wed, 05 Sep 2018 08:52:05 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 10:12:11 GMT
RUN set -ex &&     apt-get update && apt-get install -y gpg dirmngr --no-install-recommends &&     rm -rf /var/lib/apt/lists/* &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Wed, 05 Sep 2018 10:14:53 GMT
ENV CHRONOGRAF_VERSION=1.6.1
# Wed, 05 Sep 2018 10:15:52 GMT
RUN ARCH= && dpkgArch="$(dpkg --print-architecture)" &&     case "${dpkgArch##*-}" in       amd64) ARCH='amd64';;       arm64) ARCH='arm64';;       armhf) ARCH='armhf';;       armel) ARCH='armel';;       *)     echo "Unsupported architecture: ${dpkgArch}"; exit 1;;     esac &&     set -x &&     apt-get update && apt-get install -y ca-certificates curl --no-install-recommends &&     rm -rf /var/lib/apt/lists/* &&     curl -SLO "https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb.asc" &&     curl -SLO "https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb" &&     gpg --batch --verify chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb.asc chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb &&     dpkg -i chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb &&     rm -f chronograf_${CHRONOGRAF_VERSION}_${ARCH}.deb* &&     apt-get purge -y --auto-remove $buildDeps
# Wed, 05 Sep 2018 10:15:53 GMT
COPY file:30de17380b1f353617f3efd8df8d07d842ebdd75d750781b20cc7588a54c918d in /usr/share/chronograf/LICENSE 
# Wed, 05 Sep 2018 10:15:54 GMT
COPY file:8cfc239e035af78ba9337d25f99200091e0d054985fe0c87e60b767d7759d99d in /usr/share/chronograf/agpl-3.0.md 
# Wed, 05 Sep 2018 10:15:55 GMT
EXPOSE 8888/tcp
# Wed, 05 Sep 2018 10:15:56 GMT
VOLUME [/var/lib/chronograf]
# Wed, 05 Sep 2018 10:15:57 GMT
COPY file:5e829c8058b054261083c78e0bc7ad8730ab2331be79c5c3e1b6b84993b3224b in /entrypoint.sh 
# Wed, 05 Sep 2018 10:15:58 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 05 Sep 2018 10:15:59 GMT
CMD ["chronograf"]
```

-	Layers:
	-	`sha256:8d586fc7919319b234c6d8676e8dc3baa39e4edf195a2dec935bdaeeb0862163`  
		Last Modified: Wed, 05 Sep 2018 09:09:38 GMT  
		Size: 20.3 MB (20331641 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd177d11ba28398cb8381eddb735605132189a44cf727b33713a8e4d1c7fb031`  
		Last Modified: Wed, 05 Sep 2018 10:16:41 GMT  
		Size: 4.1 MB (4075471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec03035dc1c7a0ba08d0749e9b6713716dfe865fc1d3a8acd05bd171399632c5`  
		Last Modified: Wed, 05 Sep 2018 10:18:49 GMT  
		Size: 20.7 MB (20700892 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:841b88bb501a1c1fc523af1bce239102991bc6a7c039cd65b09a81f2dd7d6aa2`  
		Last Modified: Wed, 05 Sep 2018 10:18:41 GMT  
		Size: 12.3 KB (12252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2eea29db3d859690839242a306a37a5e71a19e1472e59da1946a135afc6d8e2c`  
		Last Modified: Wed, 05 Sep 2018 10:18:43 GMT  
		Size: 11.9 KB (11910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f4c3692b167d819e24b52b42f3f8fd3ff542ed4ff514325ac6fafb06b686c521`  
		Last Modified: Wed, 05 Sep 2018 10:18:41 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
