## `maven:3-jdk-11-slim`

```console
$ docker pull maven@sha256:765191a747fe30abe07b9efc938d9c15835c323465d5f7c1a5d0ad2a0d26ad48
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

### `maven:3-jdk-11-slim` - linux; amd64

```console
$ docker pull maven@sha256:f3a595735dabd81792bd5d660bbe0401ec00f7df023a4929fde74d597141984b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **327.0 MB (327028451 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2f612adcd0fe7cbd15f198c7a69cbbb096c343e18caa17e98585ec985f9484cb`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 04 Sep 2018 21:20:58 GMT
ADD file:a391d9232725a03d7b21f24be4d387c1d11f905c3ba448c0a3793745ca8cc6f3 in / 
# Tue, 04 Sep 2018 21:20:58 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 01:15:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 01:15:51 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 01:15:52 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 01:15:52 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 01:15:52 GMT
ENV JAVA_HOME=/docker-java-home
# Fri, 07 Sep 2018 19:34:20 GMT
ENV JAVA_VERSION=11-ea+28
# Fri, 07 Sep 2018 19:34:20 GMT
ENV JAVA_DEBIAN_VERSION=11~28-1
# Fri, 07 Sep 2018 19:35:15 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Fri, 07 Sep 2018 19:35:15 GMT
CMD ["jshell"]
# Fri, 07 Sep 2018 20:11:43 GMT
ARG MAVEN_VERSION=3.5.4
# Fri, 07 Sep 2018 20:11:43 GMT
ARG USER_HOME_DIR=/root
# Fri, 07 Sep 2018 20:11:43 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Fri, 07 Sep 2018 20:11:44 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Fri, 07 Sep 2018 20:11:54 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Fri, 07 Sep 2018 20:11:55 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Fri, 07 Sep 2018 20:11:59 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Fri, 07 Sep 2018 20:12:00 GMT
ENV MAVEN_HOME=/usr/share/maven
# Fri, 07 Sep 2018 20:12:00 GMT
ENV MAVEN_CONFIG=/root/.m2
# Fri, 07 Sep 2018 20:12:00 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Fri, 07 Sep 2018 20:12:01 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Fri, 07 Sep 2018 20:12:01 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Fri, 07 Sep 2018 20:12:01 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:a7e1658cb0533dfcb5baa38a0ce3230fd3aea217be1a52d0b46f5521b305d608`  
		Last Modified: Tue, 04 Sep 2018 21:24:51 GMT  
		Size: 26.3 MB (26269506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:826d7fab3f2f9f524ee8ab66d9bf80ff7ce89278ff495a4c665481d069832089`  
		Last Modified: Wed, 05 Sep 2018 01:32:25 GMT  
		Size: 460.8 KB (460788 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b7705f8b8f1de989ae8e63828bc91553d1aa32563ed57bd05b21828c0ef89920`  
		Last Modified: Wed, 05 Sep 2018 01:32:25 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:346fb9b43905ab75618d23770204a6bc486e33867d3761b8a29e052036f87396`  
		Last Modified: Wed, 05 Sep 2018 01:32:24 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85d0b893cff9a535eebbeef462ccc4f1b24604bca537f73efa15f7627b6b7a11`  
		Last Modified: Fri, 07 Sep 2018 19:40:39 GMT  
		Size: 289.4 MB (289410140 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91ba05504c4726e01dd76e382a21e8aff89aa7a840a0d18d88231dffc1475047`  
		Last Modified: Fri, 07 Sep 2018 20:13:11 GMT  
		Size: 1.9 MB (1897097 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe0e5e01fa610405e7f061c703ccfa5b9765aac54a8349abda49d8e813ccf265`  
		Last Modified: Fri, 07 Sep 2018 20:13:11 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aed3d0b50456958602c889d4605b75ef49d25a73b94ce638a48a4ade5e1d5cbd`  
		Last Modified: Fri, 07 Sep 2018 20:13:12 GMT  
		Size: 9.0 MB (8989226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79fcc56ddfea931ff328703c044f97dd56919ee5b995b011c513f50aea5ef9bb`  
		Last Modified: Fri, 07 Sep 2018 20:13:10 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:191abbc85fe83692136c129ed375e47c0b74c623fd689cc5c3bedc9f0840eda3`  
		Last Modified: Fri, 07 Sep 2018 20:13:11 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; arm variant v5

```console
$ docker pull maven@sha256:150d97077bece0481454dd5091faf5c3ab927f4e4ac532cd8499999f2f78c682
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **259.6 MB (259573932 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6faacec38f79dfad0b9cd3c780410b7cfe507f72e33ebeb95eddaa0598fd9bdf`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Wed, 05 Sep 2018 08:53:37 GMT
ADD file:c7d4df0199eabe1be20064e36b7f406cc093e6e4b249fe3d5e80efbdd9d11396 in / 
# Wed, 05 Sep 2018 08:53:37 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 09:28:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 09:28:42 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 09:28:43 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 09:28:44 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 09:28:44 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 08 Sep 2018 08:54:41 GMT
ENV JAVA_VERSION=11-ea+28
# Sat, 08 Sep 2018 08:54:41 GMT
ENV JAVA_DEBIAN_VERSION=11~28-1
# Sat, 08 Sep 2018 08:55:29 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 08 Sep 2018 08:55:30 GMT
CMD ["jshell"]
# Sat, 08 Sep 2018 09:28:56 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 08 Sep 2018 09:28:57 GMT
ARG USER_HOME_DIR=/root
# Sat, 08 Sep 2018 09:28:57 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 08 Sep 2018 09:28:57 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 08 Sep 2018 09:29:12 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Sat, 08 Sep 2018 09:29:13 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Sat, 08 Sep 2018 09:29:16 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 08 Sep 2018 09:29:16 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 08 Sep 2018 09:29:16 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 08 Sep 2018 09:29:17 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 08 Sep 2018 09:29:17 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 08 Sep 2018 09:29:17 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 08 Sep 2018 09:29:17 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:242ba358ac12243e79ea9900990c026a4b2a428ee912e82307cda7137ce87b08`  
		Last Modified: Wed, 05 Sep 2018 09:02:45 GMT  
		Size: 24.0 MB (24046737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc9be3091e0f7f183201efb4d0d133657219a4951278ed991b57026f1390a136`  
		Last Modified: Wed, 05 Sep 2018 09:38:38 GMT  
		Size: 452.7 KB (452681 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:046c6149e9cffbd63a5b8711d29fa55ec8913d650f6ba47eae844fdcceb45afd`  
		Last Modified: Wed, 05 Sep 2018 09:38:38 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c93fa67f4197286b7e8493d96d73764a8a366a9fb46d90d8b4a283f649dd570a`  
		Last Modified: Sat, 08 Sep 2018 09:01:24 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf0150768499374f90d30229db72a00a5911b97fda52dbf1f719bd86ac1abac9`  
		Last Modified: Sat, 08 Sep 2018 09:01:56 GMT  
		Size: 224.3 MB (224279300 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1aef4d44a2d5ffa04e4a4b26168b6a2a798ca5dbf94a91df4816bda9158880ca`  
		Last Modified: Sat, 08 Sep 2018 09:30:14 GMT  
		Size: 1.8 MB (1804291 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6b3a44d8fbc91736bb9ae45460bd2a14555287f37fb502ee546fc88406a5c33`  
		Last Modified: Sat, 08 Sep 2018 09:30:14 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:732e8556b75d943e5a8222e7aff41bfbcc8bc752512ae41fc556874198df33df`  
		Last Modified: Sat, 08 Sep 2018 09:30:15 GMT  
		Size: 9.0 MB (8989230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a53e2a5c771864fb600710b00a87e2fa69ecf3f90e6e1082537cdff8571836a9`  
		Last Modified: Sat, 08 Sep 2018 09:30:14 GMT  
		Size: 742.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62574bb09e207a1cb2dee7a87eb286077849d3a9f0ce0d1a4860f301170fabff`  
		Last Modified: Sat, 08 Sep 2018 09:30:14 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; arm variant v7

```console
$ docker pull maven@sha256:db6f408dd2ca6529f3bb30f48055fccec9cd5980d651af059778156e002bc2b9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **282.4 MB (282350638 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0aa2903495f7ece6da6eb2bcf86ca661ab2ac847daad6ebe3430ef214ae2bdef`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 12:03:40 GMT
ADD file:430c173aee26cd9ee26f12a79095a7590ef88c7c48a0ae19a07a09942eaae79a in / 
# Tue, 17 Jul 2018 12:03:41 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:34:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:34:48 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:34:49 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:34:50 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:34:50 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 11:59:55 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 11:59:56 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 12:00:53 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 12:00:53 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 13:36:54 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 13:36:54 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 13:36:54 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 13:36:55 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 13:37:03 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 13:37:04 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 13:37:10 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 13:37:15 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 13:37:15 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 13:37:15 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 13:37:16 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 13:37:16 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 13:37:16 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:1e5341b5f8a7f0c7e651d696478846f375e478fc35a15daad21057ed34c86aa0`  
		Last Modified: Tue, 17 Jul 2018 12:16:07 GMT  
		Size: 22.1 MB (22054548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:201706a9d8742be6b39b2112a52a81180a89c547979584ec52ab950ef13a4768`  
		Last Modified: Tue, 17 Jul 2018 12:55:17 GMT  
		Size: 436.3 KB (436272 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1db9f0721f2ca238b0a84c406f829b0b7c9a960dd91b6ebd65d2e4825db85f79`  
		Last Modified: Tue, 17 Jul 2018 12:55:17 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4dc9b2cda3454dd54d9134d49524faa78c52f7dbf220f21d80d55fb384c98815`  
		Last Modified: Tue, 17 Jul 2018 12:55:17 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:943adbb2e0699122cabad595e5929c3cdbf90be50f384514c9dc29ed5231213c`  
		Last Modified: Thu, 23 Aug 2018 12:12:44 GMT  
		Size: 249.0 MB (248979934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00766965f1404188704780037efe6d08391599ab38ab731e1e8e0af352ed1637`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 1.9 MB (1888952 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4634f5f74255b7a94bd5d5c06ff84191bd1fd4b8a644278f99fd1a09618d11e`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:569a3c69f769a57e8bd9fe2a3667335999691c1303f1da1175455b594bb37ad3`  
		Last Modified: Thu, 23 Aug 2018 13:38:07 GMT  
		Size: 9.0 MB (8989237 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48fe779116f8ef06a77ec19b03888d27768451e7f9bc5a5c21cc0af4005ba48f`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ea9d686e9d8612adcf0dda29cb823c692517b26c424c8b7e6733464faab0af`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; arm64 variant v8

```console
$ docker pull maven@sha256:a8be13dd7fa67a52a9f606783262d157b476517e7b09beda07e53b44d6358bb1
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **314.1 MB (314145587 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:39ac3e15827602b22f32593ef21a36e9c251b5ff9b8f577e4a0a0651a160a742`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Wed, 05 Sep 2018 08:45:52 GMT
ADD file:24dbb552dccf9615a5e69bf23e9456e1113ecd17c0803a5b489ffed88bedfc74 in / 
# Wed, 05 Sep 2018 08:46:08 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 12:58:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 12:58:14 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 12:58:16 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 15 Sep 2018 10:18:34 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 15 Sep 2018 10:18:35 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 15 Sep 2018 10:18:36 GMT
ENV JAVA_VERSION=11-ea+28
# Sat, 15 Sep 2018 10:18:39 GMT
ENV JAVA_DEBIAN_VERSION=11~28-1
# Sat, 15 Sep 2018 10:21:10 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 15 Sep 2018 10:21:12 GMT
CMD ["jshell"]
# Sat, 15 Sep 2018 16:39:40 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 15 Sep 2018 16:39:41 GMT
ARG USER_HOME_DIR=/root
# Sat, 15 Sep 2018 16:39:42 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 15 Sep 2018 16:39:43 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 15 Sep 2018 16:40:19 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Sat, 15 Sep 2018 16:40:22 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Sat, 15 Sep 2018 16:40:34 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 15 Sep 2018 16:40:35 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 15 Sep 2018 16:40:36 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 15 Sep 2018 16:40:37 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 15 Sep 2018 16:40:39 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 15 Sep 2018 16:40:40 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 15 Sep 2018 16:40:41 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:72c8cb2fd9e6abd14d8304d2ab8f3981d9ee18081e0eec41f5a6329ad46e13dc`  
		Last Modified: Wed, 05 Sep 2018 09:03:24 GMT  
		Size: 24.4 MB (24421582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6913615f01b262099426dbf3dc8f34a66d8acdd16e1b670f80120a578455d15f`  
		Last Modified: Wed, 05 Sep 2018 13:51:40 GMT  
		Size: 446.8 KB (446802 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec43cb8ddfaa74be1577307975c3673ede54a0bdbaf3dfd3ce3f5026dc960b4c`  
		Last Modified: Wed, 05 Sep 2018 13:51:40 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7efcec23c75ed06bd0fbded98349c08c73d716b5d10ace97dc8bfd239aededa0`  
		Last Modified: Sat, 15 Sep 2018 10:40:12 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de4ecc94b943ef1a51df0abc921684c8ef6cdca3b0623853a875bf1bb7e0cf64`  
		Last Modified: Sat, 15 Sep 2018 10:41:46 GMT  
		Size: 278.4 MB (278449850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed0cc57d033e4ef35e81d928d457221e9484bfc8da513d6b1b4568e70f21fb72`  
		Last Modified: Sat, 15 Sep 2018 16:43:56 GMT  
		Size: 1.8 MB (1836431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:751cd358ae6bb365d0b4fcad8ea8ebe00e907211fa682951dade873f0f1cbd3e`  
		Last Modified: Sat, 15 Sep 2018 16:43:56 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf476b66cdb8dafd6c1571a6b7f3163c8272c5fca5ba1022efd9c8744d8048ca`  
		Last Modified: Sat, 15 Sep 2018 16:43:57 GMT  
		Size: 9.0 MB (8989222 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79c54ee38f9e37cf1cd6dbe308e5f062c00fac268057d49eda449c46b046b7cf`  
		Last Modified: Sat, 15 Sep 2018 16:43:56 GMT  
		Size: 744.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e72e3e66aa236554060ead1eb340bce9d9bb9dd958237b6f01da9eb1ef06f42`  
		Last Modified: Sat, 15 Sep 2018 16:43:55 GMT  
		Size: 362.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; 386

```console
$ docker pull maven@sha256:3d69c4987b2680736f1e5373b23b7cb0aafb55cfbb2197e7f914a9176fca2fb0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **411.0 MB (410977688 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:90ae5c62d25af1e80b651de740ee4cb39f5a90116034c53cef12f80a17ae8f48`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Wed, 05 Sep 2018 10:42:28 GMT
ADD file:d4af5b170a1dc9b1a5129aad95a449a0412bc890b20f7bcc406b10765217d72d in / 
# Wed, 05 Sep 2018 10:42:28 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 12:46:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 12:46:37 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 12:46:38 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 12:46:39 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 12:46:39 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 08 Sep 2018 18:22:52 GMT
ENV JAVA_VERSION=11-ea+28
# Sat, 08 Sep 2018 18:22:52 GMT
ENV JAVA_DEBIAN_VERSION=11~28-1
# Sat, 08 Sep 2018 18:23:49 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 08 Sep 2018 18:23:50 GMT
CMD ["jshell"]
# Sat, 08 Sep 2018 20:58:15 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 08 Sep 2018 20:58:15 GMT
ARG USER_HOME_DIR=/root
# Sat, 08 Sep 2018 20:58:15 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 08 Sep 2018 20:58:16 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 08 Sep 2018 20:58:24 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Sat, 08 Sep 2018 20:58:25 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Sat, 08 Sep 2018 20:58:27 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 08 Sep 2018 20:58:27 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 08 Sep 2018 20:58:28 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 08 Sep 2018 20:58:28 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 08 Sep 2018 20:58:28 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 08 Sep 2018 20:58:28 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 08 Sep 2018 20:58:29 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:5b7c4e2e64859070ddb846c8d1995c868828ca3f0747e700ce525cca0c668ead`  
		Last Modified: Wed, 05 Sep 2018 10:50:43 GMT  
		Size: 26.9 MB (26855389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fe790305403cfefcd04e2c7141ec9c0cdf63365ea7cb2266f45810018349d1e`  
		Last Modified: Wed, 05 Sep 2018 13:18:18 GMT  
		Size: 469.7 KB (469687 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9ab579a9b26299f67deeeff886666f4181e13e5ff5abf594e0cc6b5c92241e0`  
		Last Modified: Wed, 05 Sep 2018 13:18:18 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e627eb48e8c1bd26da91b7e08e7ef7b07c39051360609f97ce5343cdf95448b`  
		Last Modified: Sat, 08 Sep 2018 18:28:23 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd3d4171d43b680bb21c8e6860f474fb25bfdae8725b4217d6dd4f6425425742`  
		Last Modified: Sat, 08 Sep 2018 18:28:59 GMT  
		Size: 372.7 MB (372674209 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe300bb1211ad1616ae55b3794e4794fda1d413998af5279d2b4a05da9559e9a`  
		Last Modified: Sat, 08 Sep 2018 20:59:15 GMT  
		Size: 2.0 MB (1987508 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f71a9fda6b4dbd463807b26fb7e7e7b6e803a6b39931d27dddc2b65e55e5764e`  
		Last Modified: Sat, 08 Sep 2018 20:59:14 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67baf7ab0e04e7d5093b2b51b2396b7ce0771729ed837bd45d4d18685867525f`  
		Last Modified: Sat, 08 Sep 2018 20:59:15 GMT  
		Size: 9.0 MB (8989200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cac2ced8a1c68cc361c54cbfda14d13dcd2158b6d696624ad7c075742ca3d3f3`  
		Last Modified: Sat, 08 Sep 2018 20:59:14 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb14bfe6c6e0638ff63ab483988aeb551844f885e139c9035ba008c7ea9a77ce`  
		Last Modified: Sat, 08 Sep 2018 20:59:14 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; ppc64le

```console
$ docker pull maven@sha256:2a3cf1913d5d900803c90f1a49dcc7c45247cd07cc527ad30620c90bac4e4707
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **304.5 MB (304537990 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d76481819dcd7be7b65e4d6c4524e5eeb233fefad8d56c40902a7224a0e88888`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Wed, 05 Sep 2018 08:18:11 GMT
ADD file:2c83f3c9e6ae13dc30fafc9ae3805ad69b08b4da3106915ed14ab1f30f967f23 in / 
# Wed, 05 Sep 2018 08:18:11 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 11:45:54 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 11:45:55 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 11:45:59 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 11:46:06 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 11:46:08 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 08 Sep 2018 09:20:39 GMT
ENV JAVA_VERSION=11-ea+28
# Sat, 08 Sep 2018 09:20:41 GMT
ENV JAVA_DEBIAN_VERSION=11~28-1
# Sat, 08 Sep 2018 09:22:32 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 08 Sep 2018 09:22:35 GMT
CMD ["jshell"]
# Sat, 08 Sep 2018 10:35:52 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 08 Sep 2018 10:35:53 GMT
ARG USER_HOME_DIR=/root
# Sat, 08 Sep 2018 10:35:54 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 08 Sep 2018 10:36:02 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 08 Sep 2018 10:36:37 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Sat, 08 Sep 2018 10:36:40 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Sat, 08 Sep 2018 10:36:43 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 08 Sep 2018 10:36:44 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 08 Sep 2018 10:36:44 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 08 Sep 2018 10:36:45 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 08 Sep 2018 10:36:46 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 08 Sep 2018 10:36:48 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 08 Sep 2018 10:36:49 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:ad06b39b761d5d0d233a1f9ed85dd96e65a277e736303cc95163a7aff63a44ec`  
		Last Modified: Wed, 05 Sep 2018 08:23:53 GMT  
		Size: 28.7 MB (28718549 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49bca90424a7272ac7b846fddea3728bdaaae7093a26bda8e0596bdd046aa8d2`  
		Last Modified: Wed, 05 Sep 2018 12:24:45 GMT  
		Size: 458.4 KB (458392 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e875ef1b7436e18e8f4d510cd11b49d70c3cc15aadbdff5eceb47089e22b733`  
		Last Modified: Wed, 05 Sep 2018 12:24:45 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf9aef6824ef0b70fdf7e69a05a1b70568d0d0e44ba730a08a33a5b24ae916fa`  
		Last Modified: Sat, 08 Sep 2018 09:40:32 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a265d35a0b8b22aa6723f25d9824134b334489a49ccec67b052c48387f481d64`  
		Last Modified: Sat, 08 Sep 2018 09:42:04 GMT  
		Size: 264.3 MB (264313761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48c162ff9e6a1e5f5733df1771f9c5e1354768dfc5564b6247efeb834c4c676c`  
		Last Modified: Sat, 08 Sep 2018 10:38:13 GMT  
		Size: 2.1 MB (2056346 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6f7147b0dd599dee9e61d082def7be263b7b84b9041b2cde6185550ed699bbf`  
		Last Modified: Sat, 08 Sep 2018 10:38:12 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:117c92f15076bc63a0a082d7307356a177393e75bc2d513c06ff696bb9e1b1b9`  
		Last Modified: Sat, 08 Sep 2018 10:38:14 GMT  
		Size: 9.0 MB (8989245 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22c048c6abb255bb73c04b48341d7bba4b7cedd97f33ad3a408578ee4283fec4`  
		Last Modified: Sat, 08 Sep 2018 10:38:12 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af5f7a2ead1222e4c021c49fc4581319f8c156a0bd873791147ac57d30367ead`  
		Last Modified: Sat, 08 Sep 2018 10:38:12 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; s390x

```console
$ docker pull maven@sha256:491aa9b6478024957de6f6aff0c7eb49cf15de58e99a0fe5bf4d256c9d41cee3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **296.5 MB (296534514 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d55ff0a944e1739d8a947fe1a8527e312cfa5c70de5fcfc5df84d1127f06b5ff`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Wed, 05 Sep 2018 11:42:49 GMT
ADD file:7095b21d997eff90a29af9f20d020b10d14cea2f20456b08af38e55cc6c5dcfb in / 
# Wed, 05 Sep 2018 11:42:50 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 12:06:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 12:06:45 GMT
ENV LANG=C.UTF-8
# Wed, 05 Sep 2018 12:06:45 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 05 Sep 2018 12:06:46 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 05 Sep 2018 12:06:46 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 08 Sep 2018 12:08:20 GMT
ENV JAVA_VERSION=11-ea+28
# Sat, 08 Sep 2018 12:08:20 GMT
ENV JAVA_DEBIAN_VERSION=11~28-1
# Sat, 08 Sep 2018 12:09:05 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 08 Sep 2018 12:09:06 GMT
CMD ["jshell"]
# Sat, 08 Sep 2018 13:13:57 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 08 Sep 2018 13:13:58 GMT
ARG USER_HOME_DIR=/root
# Sat, 08 Sep 2018 13:13:58 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 08 Sep 2018 13:13:58 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 08 Sep 2018 13:14:07 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Sat, 08 Sep 2018 13:14:08 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Sat, 08 Sep 2018 13:14:10 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 08 Sep 2018 13:14:11 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 08 Sep 2018 13:14:11 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 08 Sep 2018 13:14:11 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 08 Sep 2018 13:14:11 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 08 Sep 2018 13:14:12 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 08 Sep 2018 13:14:12 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:0141ef1e371b0b8a4fc6d4d5118bbbf6045c295fad232833a634af2cf45bd823`  
		Last Modified: Wed, 05 Sep 2018 11:47:38 GMT  
		Size: 24.9 MB (24910961 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bc3bfe0feae05698cb0859fa53d95daee2e1eaab41cfebb8f0ce0069be8249f`  
		Last Modified: Wed, 05 Sep 2018 12:11:29 GMT  
		Size: 469.8 KB (469760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:afb38e1f6e0d29149721db25f9fbb79505806393a70c856ce96f12151c543441`  
		Last Modified: Wed, 05 Sep 2018 12:11:29 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65d0ba243945140091255d628339e0b6f1580165203f754f88934522a60c1d0b`  
		Last Modified: Sat, 08 Sep 2018 12:14:32 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84cd649beb39bd13bad954aaa884d3c9eef060016b7e970432c5f6edc5dd4122`  
		Last Modified: Sat, 08 Sep 2018 12:14:57 GMT  
		Size: 260.3 MB (260301655 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70aa225775bb7ff1b959a33b11ea69d5b0514fe201e248c6c140433bcc0bb824`  
		Last Modified: Sat, 08 Sep 2018 13:15:18 GMT  
		Size: 1.9 MB (1861224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96b2fca694ddd6cbd5bea4bebc7401be28c43852262b2a0fd44fe9fd8d565b98`  
		Last Modified: Sat, 08 Sep 2018 13:15:17 GMT  
		Size: 227.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:980731d0fc223632856b6b52eb17d3bb61d8677f2c0c2c19b98f897b16217a06`  
		Last Modified: Sat, 08 Sep 2018 13:15:19 GMT  
		Size: 9.0 MB (8989217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76ac3150a6dd5f18cd19a328d7056308d1b86a5ed8825d71763529b99847db65`  
		Last Modified: Sat, 08 Sep 2018 13:15:17 GMT  
		Size: 742.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b35ceb32bd5055d0737ae4f01f14d3157efe9ebb64accaba361a4c27c3b502b`  
		Last Modified: Sat, 08 Sep 2018 13:15:17 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
