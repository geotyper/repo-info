## `tomee:8-jre-1.7.5-plus`

```console
$ docker pull tomee@sha256:782f0881bd4e47f0f251d3d638ac2321bc342bcd31180bdb6e96fd1202fdbe21
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

### `tomee:8-jre-1.7.5-plus` - linux; amd64

```console
$ docker pull tomee@sha256:f5f96aec63cb0950b30a299d28a04a8b9217923d9c33f03c4c298df34afeea99
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **227.9 MB (227901881 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5d453273397bff9ea80cbe8fe7494fe6c3348d2f96396287ab9bd979f478e510`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:24 GMT
ADD file:58d5c21fcabcf1eec94e8676a3b1e51c5fdc2db5c7b866a761f907fa30ede4d8 in / 
# Tue, 04 Sep 2018 21:21:24 GMT
CMD ["bash"]
# Tue, 04 Sep 2018 22:33:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 04 Sep 2018 22:33:43 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 05 Sep 2018 01:23:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 01:23:14 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 01:23:15 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 01:23:15 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 01:23:15 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 05 Sep 2018 01:23:16 GMT
ENV JAVA_VERSION=8u181
# Wed, 05 Sep 2018 01:23:16 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 05 Sep 2018 01:23:16 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 05 Sep 2018 01:23:50 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 01:23:52 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 05 Sep 2018 17:29:43 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 17:29:44 GMT
RUN mkdir -p /usr/local/tomee
# Wed, 05 Sep 2018 17:29:44 GMT
WORKDIR /usr/local/tomee
# Wed, 05 Sep 2018 17:29:44 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Wed, 05 Sep 2018 17:29:47 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Wed, 05 Sep 2018 17:30:13 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Wed, 05 Sep 2018 17:30:13 GMT
EXPOSE 8080/tcp
# Wed, 05 Sep 2018 17:30:13 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:05d1a5232b461a4b35424129580054caa878cd56f100e34282510bd4b4082e4d`  
		Last Modified: Tue, 04 Sep 2018 21:25:27 GMT  
		Size: 45.3 MB (45310060 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5cee356eda6bfe3a5a229cd3d964e722ade1da4381842b24e943b03a37aec1f2`  
		Last Modified: Tue, 04 Sep 2018 22:52:43 GMT  
		Size: 10.7 MB (10740429 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89d3385f0fd3c0c904ff6e87195bb46f5d9d309e8ddd91bc9b20855d103eeffb`  
		Last Modified: Tue, 04 Sep 2018 22:52:42 GMT  
		Size: 4.3 MB (4336162 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65dd87f6620b41e303b5ee5be4bf7b4cb3a8ee55e86123d6637737383d3078d3`  
		Last Modified: Wed, 05 Sep 2018 01:41:50 GMT  
		Size: 852.9 KB (852884 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78a183a01190c57eb606a72e8c273630224ae454d26bc3f73f4edf205821553b`  
		Last Modified: Wed, 05 Sep 2018 01:41:50 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a4499c85f9798901010eb0cd0c245a1439b731362a46d5ee246f2ad56d72fc0`  
		Last Modified: Wed, 05 Sep 2018 01:41:50 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c9d39b4bfc1b2ce067f6a3f00395918187829d4e3d5094276db7e2addd1dc1f`  
		Last Modified: Wed, 05 Sep 2018 01:42:17 GMT  
		Size: 122.1 MB (122122653 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b1cec2222c9250bed824daddb12fe4674a55afc78207ee3e3e7a943fc9293fa`  
		Last Modified: Wed, 05 Sep 2018 01:41:50 GMT  
		Size: 246.7 KB (246694 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ba88b2820c20549d80aabbc4bbfb2028b279e483c4a832dd47ed321b096db59`  
		Last Modified: Wed, 05 Sep 2018 17:33:27 GMT  
		Size: 150.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d62ddd251c348e751b6e79b17d39d925229fc475d02aed84836443949697d2a`  
		Last Modified: Wed, 05 Sep 2018 17:33:26 GMT  
		Size: 26.8 KB (26809 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0914f991a06f38739b57b133d9888fa038558f3ca08fd1a031d8477959dc15b7`  
		Last Modified: Wed, 05 Sep 2018 17:34:13 GMT  
		Size: 44.3 MB (44265662 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomee:8-jre-1.7.5-plus` - linux; arm variant v5

```console
$ docker pull tomee@sha256:a8e57493da2c00ef6516a8f99be03df2b5eb4c13098fdcf8653a58a4faeb9420
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **215.3 MB (215286159 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c7069eae5da0de3e76e25e07184cefcc03c04b987cd8cf289ba2cb8b355a7131`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 05 Sep 2018 08:54:58 GMT
ADD file:2301eb998a2cf644d62951808894ec7ace20df38ed4e82f7ab477d8a9043b67b in / 
# Wed, 05 Sep 2018 08:54:59 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 09:58:28 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 09:58:37 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 05 Sep 2018 14:27:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 14:27:09 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 14:27:10 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 14:27:11 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 14:27:12 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 05 Sep 2018 14:27:12 GMT
ENV JAVA_VERSION=8u181
# Wed, 05 Sep 2018 14:27:12 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 05 Sep 2018 14:27:13 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 05 Sep 2018 14:28:03 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 14:28:08 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 05 Sep 2018 18:06:24 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 18:06:25 GMT
RUN mkdir -p /usr/local/tomee
# Wed, 05 Sep 2018 18:06:25 GMT
WORKDIR /usr/local/tomee
# Wed, 05 Sep 2018 18:06:26 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Wed, 05 Sep 2018 18:06:30 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Wed, 05 Sep 2018 18:07:29 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Wed, 05 Sep 2018 18:07:30 GMT
EXPOSE 8080/tcp
# Wed, 05 Sep 2018 18:07:30 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:9cb1890a5e52c7c05eedad090ff39b863a62697e36cd9b3ff608dc0f832d5687`  
		Last Modified: Wed, 05 Sep 2018 09:03:55 GMT  
		Size: 44.0 MB (44033002 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe41b212ad18ceb0a81a3f52fa8c618a0bbe47fd82200767851c667ef25f51d8`  
		Last Modified: Wed, 05 Sep 2018 10:11:48 GMT  
		Size: 9.8 MB (9810215 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:836b37f3f7096f6d14a8f575975e8e27092177c0480bbe64d2f9afd752d48fab`  
		Last Modified: Wed, 05 Sep 2018 10:11:45 GMT  
		Size: 4.2 MB (4153723 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b669e5be012c0996815b3de63de3ed47710b24717fcd05159a5f736271043136`  
		Last Modified: Wed, 05 Sep 2018 14:40:30 GMT  
		Size: 845.9 KB (845878 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b1f3e0c2f3480ba960435155e84e4cdae48961cea3da9de59241ea2cc8d33d8`  
		Last Modified: Wed, 05 Sep 2018 14:41:51 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:869cc67529ccdaef0d9b1355a715f86b42aa4d1137cafa5e6ab656c4ff4527a6`  
		Last Modified: Wed, 05 Sep 2018 14:40:30 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7f62f721066752d3fd1b4e1fe292990dab84ea93c51520fbb06c65818f5f93d`  
		Last Modified: Wed, 05 Sep 2018 14:41:01 GMT  
		Size: 111.9 MB (111903271 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d301167afb12c6f10391102ef4c700b8976347dfb18af062d882ffed0f78626f`  
		Last Modified: Wed, 05 Sep 2018 14:40:30 GMT  
		Size: 246.7 KB (246737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84043dad1c2baf000803dc47bfb129914ce73b498bf4ab93d224e34b428dfc44`  
		Last Modified: Wed, 05 Sep 2018 18:14:11 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9839ecbda6abf0cea4eeecd0ca869198384004cea23415d1bb77d0408ceadd7b`  
		Last Modified: Wed, 05 Sep 2018 18:14:11 GMT  
		Size: 26.9 KB (26857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f52f70108cc414d3092ff7f668184bfae7a06f24a2d548f5d734cb28ba9b80db`  
		Last Modified: Wed, 05 Sep 2018 18:14:52 GMT  
		Size: 44.3 MB (44265914 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomee:8-jre-1.7.5-plus` - linux; arm variant v7

```console
$ docker pull tomee@sha256:bfb23178f27be7b4e1d6d04d28e9cdd5e0a09f34fd43765862d8fdb4d6a55441
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **240.3 MB (240346541 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a663d8537971f3710e6a244a3fc15ce2cef73231bf1c4229e535350f9a81ece4`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Sat, 28 Apr 2018 12:04:18 GMT
ADD file:c7fba27b02c4bda63faef7eb30156a55feb4c0e9ecd529a24dd8d62942c2f83c in / 
# Sat, 28 Apr 2018 12:04:19 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:13:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:13:58 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:59:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:59:16 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:59:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:59:18 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:59:18 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 12:59:19 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 12:59:27 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 12:59:27 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Sat, 05 May 2018 13:00:26 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 05 May 2018 13:00:28 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Sat, 05 May 2018 15:31:33 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 05 May 2018 15:31:34 GMT
RUN mkdir -p /usr/local/tomee
# Sat, 05 May 2018 15:31:34 GMT
WORKDIR /usr/local/tomee
# Sat, 05 May 2018 15:31:35 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Sat, 05 May 2018 15:31:39 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Sat, 05 May 2018 15:32:38 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Sat, 05 May 2018 15:32:38 GMT
EXPOSE 8080/tcp
# Sat, 05 May 2018 15:32:38 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:5483105d09166836731e940c850827dd1a4fe16b04d1921eea4d8da7c98e99bc`  
		Last Modified: Sat, 28 Apr 2018 12:15:18 GMT  
		Size: 42.1 MB (42063737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ed57f83cc7c78757972312a1b5a30524f861523c5390d062845f18c696f48ea`  
		Last Modified: Sat, 05 May 2018 12:35:37 GMT  
		Size: 9.5 MB (9472475 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:859203aede279201e8caf07cf2963456c56bac72a64071079dc9db6fb65ed1a2`  
		Last Modified: Sat, 05 May 2018 12:35:34 GMT  
		Size: 3.9 MB (3912835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df26ddf71ea9e82f175e400809b8f06871dd0937c5a90f4ffe95286544a9f719`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 830.3 KB (830332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2c21322a9c89724512d6ea5faa10299c60c8a605d6f563c84c28177db8d2770`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2270f04a4be61f52577232813fff92e797d3fc190d52f71411afc26b0911f8e4`  
		Last Modified: Sat, 05 May 2018 13:29:04 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da2dc1aba58c8cd285639cac6b03c823e5fcdb91aa8922652e7d9387aaca6fa4`  
		Last Modified: Sat, 05 May 2018 13:29:37 GMT  
		Size: 139.5 MB (139501760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02869ec2bb3864b06abd435610eb6849d5c62426517de1a603ef6fe43c7d3815`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 272.1 KB (272082 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:86b2945e8eb5c51597eeaa0b9140cd51356fdea2bdbc0e85b10b3004a32453fc`  
		Last Modified: Sat, 05 May 2018 15:39:04 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b50677ccf4d3bf28f894c2b3e1b114ba522dfb82efd8068fb1536596aa68749a`  
		Last Modified: Sat, 05 May 2018 15:39:04 GMT  
		Size: 26.9 KB (26854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:378210a621c561f0e0f6103acdd6491c67118d16bd5a95c91852795cc9c44c2f`  
		Last Modified: Sat, 05 May 2018 15:39:54 GMT  
		Size: 44.3 MB (44265907 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomee:8-jre-1.7.5-plus` - linux; arm64 variant v8

```console
$ docker pull tomee@sha256:8b07cb39d6f6044cd6530a7cb0e6cbe3ca3a4f1a762c28ff8789acdba36bc03c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **215.0 MB (215031846 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fb01227618f010efe9c1e07a95dba4516c40a76c4c5b87320065b1d4aff60927`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 05 Sep 2018 08:50:16 GMT
ADD file:4e01bc399974f6fe22cd2b4421c2e52c52380aa00a770986939071dbc59d734e in / 
# Wed, 05 Sep 2018 08:50:30 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 10:02:26 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 10:02:44 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 05 Sep 2018 13:33:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 13:33:19 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 13:33:21 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 13:33:23 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 13:33:24 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 05 Sep 2018 13:33:24 GMT
ENV JAVA_VERSION=8u181
# Wed, 05 Sep 2018 13:33:25 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 05 Sep 2018 13:33:26 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 05 Sep 2018 13:39:19 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 13:39:24 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 06 Sep 2018 04:12:46 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 06 Sep 2018 04:12:48 GMT
RUN mkdir -p /usr/local/tomee
# Thu, 06 Sep 2018 04:12:48 GMT
WORKDIR /usr/local/tomee
# Thu, 06 Sep 2018 04:12:49 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Thu, 06 Sep 2018 04:12:55 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Thu, 06 Sep 2018 04:15:29 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Thu, 06 Sep 2018 04:15:29 GMT
EXPOSE 8080/tcp
# Thu, 06 Sep 2018 04:15:30 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:421608e4e92275f9265604523f9299cf5f4bd493a1ea3affd62c265b38fc8823`  
		Last Modified: Wed, 05 Sep 2018 09:06:53 GMT  
		Size: 43.1 MB (43123621 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:185ac5864132647baf5fa26dfe782dbf1645944aca4a8e963d24572bb0b90007`  
		Last Modified: Wed, 05 Sep 2018 10:25:53 GMT  
		Size: 9.7 MB (9690090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c69d98c830cad0499c1720f09b5ec6e3dde0f144f0b5ab1b555fa37e4eac6623`  
		Last Modified: Wed, 05 Sep 2018 10:25:51 GMT  
		Size: 4.1 MB (4088370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:624115d32e82854c6017d240b844b48870d37742c5860868c7662271ef22641a`  
		Last Modified: Wed, 05 Sep 2018 14:16:14 GMT  
		Size: 839.1 KB (839091 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e985da6c2c9cf20205643ae0b0e1ab408179d3b01799dafd60483471bbfbc63`  
		Last Modified: Wed, 05 Sep 2018 14:16:14 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8f8679788920f265c6cfb8631f5f7cb32a6d16cc263152ce0e918de7b0be445`  
		Last Modified: Wed, 05 Sep 2018 14:16:13 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db339c1ad3619a5cac5b8048375669970b143a93db943302430ccdc984d68714`  
		Last Modified: Wed, 05 Sep 2018 14:16:47 GMT  
		Size: 112.8 MB (112750981 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6819153e1327d9a21df22c55cd85bdb0bac37427bec941fc0eb36cf3cdb29beb`  
		Last Modified: Wed, 05 Sep 2018 14:16:14 GMT  
		Size: 246.7 KB (246666 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:821eb378fd9b65b484c1d209a9857f20df56c073f1856257fdf8da3f35829dd6`  
		Last Modified: Thu, 06 Sep 2018 04:32:14 GMT  
		Size: 150.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:764f99065a4d8af7f62ad1a40923e726e68d20318e14e5515e3e83b01bc120aa`  
		Last Modified: Thu, 06 Sep 2018 04:32:13 GMT  
		Size: 26.8 KB (26827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2b409f0e3604b3c492730c57a64dafd1a369c757dbf0e0aab232188b692f917`  
		Last Modified: Thu, 06 Sep 2018 04:33:47 GMT  
		Size: 44.3 MB (44265672 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomee:8-jre-1.7.5-plus` - linux; 386

```console
$ docker pull tomee@sha256:5467ac6587672e373c1e82465e718597159c66c43970494cf51527ed4c3f7aad
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **229.3 MB (229342555 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d0c70a0eb119abc380daefaf7ec5e4adb2def47c49c1c2a2d49863c1428bade2`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 05 Sep 2018 10:43:36 GMT
ADD file:3712892f37687a2c2c5bbcb861ce5514725fe71d82c86a79fb1d1bcaa39b8989 in / 
# Wed, 05 Sep 2018 10:43:36 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 11:39:44 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 11:39:55 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 05 Sep 2018 12:59:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 12:59:54 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 12:59:55 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 12:59:56 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 12:59:56 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 05 Sep 2018 12:59:56 GMT
ENV JAVA_VERSION=8u181
# Wed, 05 Sep 2018 12:59:57 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 05 Sep 2018 12:59:57 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 05 Sep 2018 13:01:22 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 13:01:28 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Fri, 07 Sep 2018 04:08:33 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 07 Sep 2018 04:08:34 GMT
RUN mkdir -p /usr/local/tomee
# Fri, 07 Sep 2018 04:08:34 GMT
WORKDIR /usr/local/tomee
# Fri, 07 Sep 2018 04:08:34 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Fri, 07 Sep 2018 04:08:38 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Fri, 07 Sep 2018 04:09:06 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Fri, 07 Sep 2018 04:09:06 GMT
EXPOSE 8080/tcp
# Fri, 07 Sep 2018 04:09:06 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:23bbbdd93c8977020ec67716d0cda1fe7a96e73c4c3a0aa6c42122459e2ba839`  
		Last Modified: Wed, 05 Sep 2018 10:51:53 GMT  
		Size: 46.0 MB (46039046 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0651aebef484f2932d9d9ec0ecaeaa15733b8454c24edd2fce38adb0542d794`  
		Last Modified: Wed, 05 Sep 2018 12:09:00 GMT  
		Size: 10.8 MB (10752740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5868a2cc4b3fe4d148aaea3d9f4da71a92f29f3b899d163fef3a2ead52cf44a6`  
		Last Modified: Wed, 05 Sep 2018 12:08:55 GMT  
		Size: 4.6 MB (4555338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4dd35c023594c2930ba4cb3209aa37855e7837d3d47f26e8815ab91e4c0ec5ed`  
		Last Modified: Wed, 05 Sep 2018 13:26:52 GMT  
		Size: 861.8 KB (861782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7804c3aaf013cbb9bbaf815ba41ef27829d0403865a7f6344ce8e2d2efec0ffd`  
		Last Modified: Wed, 05 Sep 2018 13:26:52 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0629a6b86449b3633c75a6ccd7d7b22c9abaf644468b6b257df646d07e051ec8`  
		Last Modified: Wed, 05 Sep 2018 13:26:52 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9597f493d0a66ba22d6256f9f43f01665a456c3204a47c06fc32dd5620471a56`  
		Last Modified: Wed, 05 Sep 2018 13:27:45 GMT  
		Size: 122.6 MB (122593836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ae4b9c20f72fb1df73606e43aecca65a5e947941629efbb960f5c3939769989`  
		Last Modified: Wed, 05 Sep 2018 13:26:52 GMT  
		Size: 246.8 KB (246815 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8722e845d398af116f57383da09b1f8c73f26f4025bb790fb237b503b535baca`  
		Last Modified: Fri, 07 Sep 2018 04:12:06 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84cc112d5bd592f2fe5ec9c83da9c43fd742a0cc52c99a9be93845e1b8607b3e`  
		Last Modified: Fri, 07 Sep 2018 04:12:07 GMT  
		Size: 26.8 KB (26811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71d72cf065ab041dced404cce6382618ed88580a6b25fac0a44393e1dad2fb83`  
		Last Modified: Fri, 07 Sep 2018 04:12:31 GMT  
		Size: 44.3 MB (44265659 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomee:8-jre-1.7.5-plus` - linux; ppc64le

```console
$ docker pull tomee@sha256:b62172196806c9dff85acacdaa3c80435d6b170279d03cd8cf02fe2913c46075
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **219.8 MB (219751973 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:48a7e04bc1f7484b00fdb8fe323d345327f2132382ad3ae2d7b0293253552556`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 05 Sep 2018 08:19:18 GMT
ADD file:f98c8d96684a432f8bb2cc0b184e5357631ed2431085de5814f32fe8eb28a4b9 in / 
# Wed, 05 Sep 2018 08:19:19 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 09:04:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 09:04:57 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 05 Sep 2018 12:12:31 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 12:12:32 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 12:12:36 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 12:12:38 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 12:12:42 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 05 Sep 2018 12:12:43 GMT
ENV JAVA_VERSION=8u181
# Wed, 05 Sep 2018 12:12:45 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 05 Sep 2018 12:12:45 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 05 Sep 2018 12:15:59 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 12:16:02 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 05 Sep 2018 18:01:29 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 18:01:31 GMT
RUN mkdir -p /usr/local/tomee
# Wed, 05 Sep 2018 18:01:32 GMT
WORKDIR /usr/local/tomee
# Wed, 05 Sep 2018 18:01:33 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Wed, 05 Sep 2018 18:01:49 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Wed, 05 Sep 2018 18:02:50 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Wed, 05 Sep 2018 18:02:53 GMT
EXPOSE 8080/tcp
# Wed, 05 Sep 2018 18:02:53 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:c931e468b38019a7817d974db9ed0b4ae9d1765d297590669406c18589ffae5e`  
		Last Modified: Wed, 05 Sep 2018 08:25:26 GMT  
		Size: 45.6 MB (45595396 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d6ce5ff3d103c074bf719d23bd00cf4926a1a9e032e7e3307eaa65233308ab2`  
		Last Modified: Wed, 05 Sep 2018 09:17:40 GMT  
		Size: 9.9 MB (9943043 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0609146a0edf97fdccccb147946f1c5d48516f95535168e016a048d486209f9`  
		Last Modified: Wed, 05 Sep 2018 09:17:38 GMT  
		Size: 4.3 MB (4289760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39156284a62bd5fa9f12e46aa8325401d0bcc29ccc74a7cdb70c8c7e7b4b5ad1`  
		Last Modified: Wed, 05 Sep 2018 12:36:53 GMT  
		Size: 848.3 KB (848303 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ab707bfd8a31c5233be5ac37b43ee96a89978e0f2026d8310f102b0830e6907`  
		Last Modified: Wed, 05 Sep 2018 12:36:48 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:690f6ed7b9ae2e64761814c38c74a37f2cf20b22340d69297776970d5ccab8a2`  
		Last Modified: Wed, 05 Sep 2018 12:36:49 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99f8d8d1e58aa320b1db885fb7368d840c45a1c1421259fbfc1cbe035dcd5056`  
		Last Modified: Wed, 05 Sep 2018 12:37:15 GMT  
		Size: 114.5 MB (114535473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e67e166bfb789e37fc1ad0419256b07e4cec10dbc01072354b9450af0b01447`  
		Last Modified: Wed, 05 Sep 2018 12:36:48 GMT  
		Size: 246.7 KB (246659 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fea4a2d4d3f0d952a516be702ee135aa3841085dd809a1ca31492d2626b6c0ce`  
		Last Modified: Wed, 05 Sep 2018 18:12:47 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7913a97ff653e4df06b05031f45c896ad13f1d3eeed5f01e18cd3985900475e`  
		Last Modified: Wed, 05 Sep 2018 18:12:47 GMT  
		Size: 26.9 KB (26865 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb88c9cc3d97895e1cf430b32e52431ede6ef30e25ea7cfaf08af0c1489cad9d`  
		Last Modified: Wed, 05 Sep 2018 18:13:40 GMT  
		Size: 44.3 MB (44265910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomee:8-jre-1.7.5-plus` - linux; s390x

```console
$ docker pull tomee@sha256:abd509a04d0f7a9c9e034b209989dc0fe7908a3a9066e1e475dddbe9b10b768e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **219.4 MB (219373018 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ba6713910a9fa5e841a31979ac7a55e834b0c9c3b7ad3035f910710aa5aa17e7`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 05 Sep 2018 11:43:59 GMT
ADD file:e8d7ae40251e43d792ae1b2a67f12263d8a7bbdb75e0b43b488b1e3a4beb6ad2 in / 
# Wed, 05 Sep 2018 11:44:00 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 12:44:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 12:44:16 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 05 Sep 2018 18:19:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 18:19:36 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 18:19:38 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 18:19:39 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 18:19:39 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 05 Sep 2018 18:19:39 GMT
ENV JAVA_VERSION=8u181
# Wed, 05 Sep 2018 18:19:39 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 05 Sep 2018 18:19:40 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 05 Sep 2018 18:20:36 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 18:20:39 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 05 Sep 2018 19:52:05 GMT
ENV PATH=/usr/local/tomee/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 19:52:06 GMT
RUN mkdir -p /usr/local/tomee
# Wed, 05 Sep 2018 19:52:06 GMT
WORKDIR /usr/local/tomee
# Wed, 05 Sep 2018 19:52:06 GMT
ENV GPG_KEYS=BDD0BBEB753192957EFC5F896A62FC8EF17D8FEF 	223D3A74B068ECA354DC385CE126833F9CF64915 	7A2744A8A9AAF063C23EB7868EBE7DBE8D050EEF 	82D8419BA697F0E7FB85916EE91287822FDB81B1 	9056B710F1E332780DE7AF34CBAEBE39A46C4CA1 	A57DAF81C1B69921F4BA8723A8DE0A4DB863A7C1 	B7574789F5018690043E6DD9C212662E12F3E1DD 	B8B301E6105DF628076BD92C5483E55897ABD9B9 	DBCCD103B8B24F86FFAAB025C8BB472CD297D428 	F067B8140F5DD80E1D3B5D92318242FE9A0B1183 	FAA603D58B1BA4EDF65896D0ED340E0E6D545F97
# Wed, 05 Sep 2018 19:52:10 GMT
RUN set -xe 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Wed, 05 Sep 2018 20:05:04 GMT
RUN set -x 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz.asc -o tomee.tar.gz.asc 	&& curl -fSL http://repo.maven.apache.org/maven2/org/apache/openejb/apache-tomee/1.7.5/apache-tomee-1.7.5-plus.tar.gz -o tomee.tar.gz 	&& gpg --batch --verify tomee.tar.gz.asc tomee.tar.gz 	&& tar -zxf tomee.tar.gz 	&& mv apache-tomee-plus-1.7.5/* /usr/local/tomee 	&& rm -Rf apache-tomee-plus-1.7.5 	&& rm bin/*.bat 	&& rm tomee.tar.gz*
# Wed, 05 Sep 2018 20:05:05 GMT
EXPOSE 8080/tcp
# Wed, 05 Sep 2018 20:05:05 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:0d67503d3ff96f2ecf56e6f53b6d10b562227891864b38cd82deb47291f67e4d`  
		Last Modified: Wed, 05 Sep 2018 11:48:33 GMT  
		Size: 45.2 MB (45199628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:731e997f60fe12a280a40cdbd86b8fe3795ca59b89f45d0841452af5b02a4320`  
		Last Modified: Wed, 05 Sep 2018 12:50:09 GMT  
		Size: 10.3 MB (10267363 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a92ce7dc85129d33f197d8718147806c5536dc3af5f6311cb463357e64c4f789`  
		Last Modified: Wed, 05 Sep 2018 12:50:07 GMT  
		Size: 4.4 MB (4366746 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7948c50be20d4d869842584a0e9a0460af873dc43c490cee5757c725600455f`  
		Last Modified: Wed, 05 Sep 2018 18:28:24 GMT  
		Size: 863.6 KB (863644 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbfb65f3fec09d5186c74a1fe3d707342bbdee710726e3c4e3e00c76e4ae5f3b`  
		Last Modified: Wed, 05 Sep 2018 18:28:23 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03d306b3481293d975712e2d4ed385d0f57de5809f0dece7189ff702bc3c7ca7`  
		Last Modified: Wed, 05 Sep 2018 18:28:24 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:52927b593aecbf43551442f767e471be69e9e740e144890e2c1e7202fe2941a4`  
		Last Modified: Wed, 05 Sep 2018 18:28:49 GMT  
		Size: 114.1 MB (114135858 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df7bf7e38c0d9b32af76a689a64ea8219570ed4a66b05a1926f658f156133d19`  
		Last Modified: Wed, 05 Sep 2018 18:28:24 GMT  
		Size: 246.7 KB (246730 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ffac8f034b8c802076eeef95f9066656b4015b1fab09b92303af865f187d5dcd`  
		Last Modified: Wed, 05 Sep 2018 20:13:02 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a004c77cdd48ab85a0851b915d9d298de693e61390d1dd573e77ac670662e00`  
		Last Modified: Wed, 05 Sep 2018 20:13:02 GMT  
		Size: 26.8 KB (26824 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc7328d30740d2f9c2239e88e5f97312e30603ab0f3837f4a1a0d94f5d9de0e7`  
		Last Modified: Wed, 05 Sep 2018 20:13:32 GMT  
		Size: 44.3 MB (44265696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
