## `gradle:jdk7-slim`

```console
$ docker pull gradle@sha256:6823e4b318ceaee63358cab64d933060b588bdb449b14170d977f8981b21a14a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; 386

### `gradle:jdk7-slim` - linux; amd64

```console
$ docker pull gradle@sha256:574a6f3992a288e1a37a5beb6d9f71200492920dd86139bcd26c597376f4520c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **206.6 MB (206579722 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5e7fd05c6d0d7deeddcee9a282a281e2af2af1239d8e630a57a96c46bcdec820`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 04 Sep 2018 21:20:04 GMT
ADD file:95eda454ef09779bfb9e8ba5744d0630fb6f59eb4c9174efa44804a756d15df3 in / 
# Tue, 04 Sep 2018 21:20:05 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 01:26:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 01:26:42 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 01:26:43 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 01:26:43 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 01:26:43 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 05 Sep 2018 01:26:44 GMT
ENV JAVA_VERSION=7u181
# Wed, 05 Sep 2018 01:26:44 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Wed, 05 Sep 2018 01:27:44 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 15:04:15 GMT
CMD ["gradle"]
# Wed, 05 Sep 2018 15:04:15 GMT
ENV GRADLE_HOME=/opt/gradle
# Mon, 24 Sep 2018 20:20:46 GMT
ENV GRADLE_VERSION=4.10.2
# Mon, 24 Sep 2018 20:21:06 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Mon, 24 Sep 2018 20:21:06 GMT
ARG GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
# Mon, 24 Sep 2018 20:21:09 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Mon, 24 Sep 2018 20:21:10 GMT
USER [gradle]
# Mon, 24 Sep 2018 20:21:10 GMT
VOLUME [/home/gradle/.gradle]
# Mon, 24 Sep 2018 20:21:10 GMT
WORKDIR /home/gradle
# Mon, 24 Sep 2018 20:21:12 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:57936531d1eea907ae6c73ebe8f8b5dc71232f5a642db22e877a4f0fc6ff1516`  
		Last Modified: Tue, 04 Sep 2018 21:23:28 GMT  
		Size: 30.1 MB (30120564 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2298fd4ed9840c0f93526d2c58380cf647aa4579e0fa6eae9c6b2cae2a19f7eb`  
		Last Modified: Wed, 05 Sep 2018 01:43:48 GMT  
		Size: 463.7 KB (463743 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40c7c6172ee282cedb73af91509beee5d91b6d5b3b7d35c8f05b7b0cd499145f`  
		Last Modified: Wed, 05 Sep 2018 01:43:48 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bf960a7af9a0a2e14f22b99bdf374464ae406f18ee32cacbfdb8eac4bd05405`  
		Last Modified: Wed, 05 Sep 2018 01:43:48 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:763025732983aaeaffa4afff6b2c97fb6feea7a5366aaf704208877c9facaa28`  
		Last Modified: Wed, 05 Sep 2018 01:44:01 GMT  
		Size: 85.2 MB (85205048 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d139f6c858b673f68e65fc41695242536debb7da49da074db50129b3b506f16d`  
		Last Modified: Mon, 24 Sep 2018 20:28:21 GMT  
		Size: 12.4 MB (12384137 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:108cfe5e6817b0a5a7ec998ae6b71a3c292e0d04d08e7beb27d5d532d070ced6`  
		Last Modified: Mon, 24 Sep 2018 20:28:26 GMT  
		Size: 78.4 MB (78405712 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75f78c2fa194a0871683346a30c24265bbd47ac1902150b6469c7bd50fd75af`  
		Last Modified: Mon, 24 Sep 2018 20:28:19 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jdk7-slim` - linux; arm variant v5

```console
$ docker pull gradle@sha256:33cb3af2b5bd1560d0c7f304af4b48966e7b44e6d341dbc20c1be213d9631af2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **191.7 MB (191666229 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:aa2f8cbf9349fcc65c500096de891e126d0221b75c60e40820ba84dda7a611ba`
-	Default Command: `["gradle"]`

```dockerfile
# Wed, 05 Sep 2018 08:50:35 GMT
ADD file:1922873efedf87e0caa2cf6abb867e47d7accfbfefc1bf7531b75e29fe37de07 in / 
# Wed, 05 Sep 2018 08:50:36 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 09:35:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 09:35:16 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 09:35:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 09:35:18 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 09:35:18 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 05 Sep 2018 09:35:18 GMT
ENV JAVA_VERSION=7u181
# Wed, 05 Sep 2018 09:35:19 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Wed, 05 Sep 2018 09:36:51 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 14:07:33 GMT
CMD ["gradle"]
# Wed, 05 Sep 2018 14:07:34 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 25 Sep 2018 08:49:36 GMT
ENV GRADLE_VERSION=4.10.2
# Tue, 25 Sep 2018 08:50:24 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 25 Sep 2018 08:50:25 GMT
ARG GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
# Tue, 25 Sep 2018 08:50:32 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 25 Sep 2018 08:50:37 GMT
USER [gradle]
# Tue, 25 Sep 2018 08:50:37 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 25 Sep 2018 08:50:38 GMT
WORKDIR /home/gradle
# Tue, 25 Sep 2018 08:50:42 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:d9dec235236bca9c64333dbfb092d7a058ef623c6ba80d027962a1196ec006d9`  
		Last Modified: Wed, 05 Sep 2018 09:00:01 GMT  
		Size: 28.4 MB (28430740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6a245f95ad46b15c78ec19eb0d32f981a711a9e37a232279c86281687a39306`  
		Last Modified: Wed, 05 Sep 2018 09:44:21 GMT  
		Size: 456.4 KB (456444 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba25b8e00f177f6e1247013c6ecf636f768670af2925c9f7363d76420407ebd4`  
		Last Modified: Wed, 05 Sep 2018 09:44:20 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b532d67597d91cef35fd564ccf339cd65f5e002856ae29bcb3f52d56c2e44856`  
		Last Modified: Wed, 05 Sep 2018 09:44:20 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:676ec729eb48c631774946da830d55cf7a21dcfdabb2748a99504118c745e33e`  
		Last Modified: Wed, 05 Sep 2018 09:44:33 GMT  
		Size: 72.2 MB (72181641 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8b7fdb4b82409a15a9441fa548782fe18e846583807ed7aa6bccff28c523f87`  
		Last Modified: Tue, 25 Sep 2018 09:00:16 GMT  
		Size: 12.2 MB (12191195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32a345b6016e2bb7918cd9e482df229254c4d1f35b808f92dd483c21d8f2e828`  
		Last Modified: Tue, 25 Sep 2018 09:00:24 GMT  
		Size: 78.4 MB (78405595 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5c0459d61d4be1d759573e25f22fe2ef5d6372d236d1f591f33b52e60137a9a4`  
		Last Modified: Tue, 25 Sep 2018 09:00:12 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jdk7-slim` - linux; arm variant v7

```console
$ docker pull gradle@sha256:7e512dc9f5aa8dcd49853feeb593c75b5a4f75f705987a7fc79685aec60c5033
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **187.7 MB (187681874 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6dd8d7faa6ca900078564b43cdfc02f1522ba47e4d928fba171a9841de00c550`
-	Default Command: `["gradle"]`

```dockerfile
# Wed, 05 Sep 2018 11:59:41 GMT
ADD file:e98fce6ce6aee310f31c67240c7a9f8cb7de0e6deb0967029e5528255c7a86f0 in / 
# Wed, 05 Sep 2018 11:59:45 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 13:27:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 13:27:59 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 13:28:00 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 13:28:02 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 13:28:02 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 05 Sep 2018 13:28:02 GMT
ENV JAVA_VERSION=7u181
# Wed, 05 Sep 2018 13:28:03 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Wed, 05 Sep 2018 13:29:15 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 05 Sep 2018 17:51:57 GMT
CMD ["gradle"]
# Wed, 05 Sep 2018 17:51:58 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 25 Sep 2018 12:00:37 GMT
ENV GRADLE_VERSION=4.10.2
# Tue, 25 Sep 2018 12:01:18 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 25 Sep 2018 12:01:19 GMT
ARG GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
# Tue, 25 Sep 2018 12:01:27 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 25 Sep 2018 12:01:27 GMT
USER [gradle]
# Tue, 25 Sep 2018 12:01:28 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 25 Sep 2018 12:01:28 GMT
WORKDIR /home/gradle
# Tue, 25 Sep 2018 12:01:32 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:e7731670a93bf29e604d72ec2b8625589828c7d950c54f459fd2fb3fb8cf6e73`  
		Last Modified: Wed, 05 Sep 2018 12:09:08 GMT  
		Size: 26.3 MB (26287004 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20732298c973041fa9dfd5140384088b681b5210d358af234f804c92ea624af8`  
		Last Modified: Wed, 05 Sep 2018 13:45:03 GMT  
		Size: 432.3 KB (432314 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306c16b05ac260bf5495a9d4e58021eaee24fbbbb56c335ef2a1c49ad0965ec0`  
		Last Modified: Wed, 05 Sep 2018 13:45:03 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1850d26c80f8e448e6e27b56b953c98e21ec755978c144ce38fc7579edac845e`  
		Last Modified: Wed, 05 Sep 2018 13:45:03 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f0c6734989760ae2cd2083cab8fcd04cc755190895509541f6f227f64a72f3d`  
		Last Modified: Wed, 05 Sep 2018 13:45:13 GMT  
		Size: 70.5 MB (70509827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:217964ea2393abb008a7a73a93a805e7a0d85700ea63dc1b9fd808a86adf7ac0`  
		Last Modified: Tue, 25 Sep 2018 12:10:31 GMT  
		Size: 12.0 MB (12046521 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46d5a4e9f9fda28622d04ac4635bd23a54537ed771a6a3cc3398ab8013126250`  
		Last Modified: Tue, 25 Sep 2018 12:10:37 GMT  
		Size: 78.4 MB (78405595 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2913e50af8b9bea7be5f7d0b4f5b4e81eb4a93d93e3b74456ef199742c002c80`  
		Last Modified: Tue, 25 Sep 2018 12:10:28 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jdk7-slim` - linux; 386

```console
$ docker pull gradle@sha256:061412b8239287f0602c0da57c36fb6bdc7f277d1c66121a7a216a87e670f1e0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **218.8 MB (218786604 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8529feefec4eae211ec32089c83dae0900de5cb5facc5745d2a841615c998939`
-	Default Command: `["gradle"]`

```dockerfile
# Wed, 05 Sep 2018 10:40:12 GMT
ADD file:2ca8426f2467f87a86e824a9ddd82e5c18a3154cacd5c74b4de6fa8de206b84c in / 
# Wed, 05 Sep 2018 10:40:12 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 13:06:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 13:06:49 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 13:06:50 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 13:06:52 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 13:06:52 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 05 Sep 2018 13:06:52 GMT
ENV JAVA_VERSION=7u181
# Wed, 05 Sep 2018 13:06:52 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Wed, 05 Sep 2018 13:09:07 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Fri, 07 Sep 2018 03:05:48 GMT
CMD ["gradle"]
# Fri, 07 Sep 2018 03:05:49 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 25 Sep 2018 10:39:29 GMT
ENV GRADLE_VERSION=4.10.2
# Tue, 25 Sep 2018 10:40:05 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 25 Sep 2018 10:40:05 GMT
ARG GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
# Tue, 25 Sep 2018 10:40:10 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 25 Sep 2018 10:40:10 GMT
USER [gradle]
# Tue, 25 Sep 2018 10:40:10 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 25 Sep 2018 10:40:10 GMT
WORKDIR /home/gradle
# Tue, 25 Sep 2018 10:40:12 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=b49c6da1b2cb67a0caf6c7480630b51c70a11ca2016ff2f555eaeda863143a29
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:3a0612442afb0e48bf3a7464b288a65842036a329ebe2e29d2c5cf2865a7eda1`  
		Last Modified: Wed, 05 Sep 2018 10:48:24 GMT  
		Size: 30.3 MB (30270069 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec388e0f3fa2dac46c15155f8c5d833c73c83c38c56ba879b7b9ee1f82c33721`  
		Last Modified: Wed, 05 Sep 2018 13:29:52 GMT  
		Size: 466.3 KB (466290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08c171584d41ec51129431a206158a478453ba12d8395205e3c8025530b52569`  
		Last Modified: Wed, 05 Sep 2018 13:29:52 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91ecedb5dbb7ded7bb71dc9d3bdfd303cc59568a829ded2c8f3b03ae675d64fa`  
		Last Modified: Wed, 05 Sep 2018 13:29:52 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6db7d236a8c1946b51d10b136454944602db831d457ca12fbabf5853c74ba9fd`  
		Last Modified: Wed, 05 Sep 2018 13:30:29 GMT  
		Size: 97.1 MB (97124036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee960c36d7cd997c5f3d95cd92263a4c4ead61dcddffedf676d96bede6e0dccf`  
		Last Modified: Tue, 25 Sep 2018 10:46:19 GMT  
		Size: 12.5 MB (12520059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfaa93032aa849a74bc2b09611a4c6aa867a69e63060f4004b47dc1dcba3354a`  
		Last Modified: Tue, 25 Sep 2018 10:46:23 GMT  
		Size: 78.4 MB (78405634 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eccc98240e1e7b75d9c365759a2831f87a253ddb589ea5131f8952f6fbf3deed`  
		Last Modified: Tue, 25 Sep 2018 10:46:16 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
