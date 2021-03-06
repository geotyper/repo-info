## `groovy:jdk-alpine`

```console
$ docker pull groovy@sha256:cf44c1be977dd89bd0675077e96acf0aa6f5b4dbaa77fb74efaa0814e5900b70
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `groovy:jdk-alpine` - linux; amd64

```console
$ docker pull groovy@sha256:e09c1834a513e91c6e50b215eb84aea7a01ad7b1b7dec3ad2d91d0dd9de4e67b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **102.6 MB (102619082 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c5285574abb9e660cd3f0beba27c55150accd9d886234190a3b70a40cc38d214`
-	Default Command: `["groovysh"]`

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
# Wed, 12 Sep 2018 04:32:13 GMT
CMD ["groovysh"]
# Wed, 12 Sep 2018 04:32:13 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 12 Sep 2018 04:32:13 GMT
ENV GROOVY_VERSION=2.5.2
# Wed, 12 Sep 2018 04:32:21 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 12 Sep 2018 04:32:25 GMT
USER [groovy]
# Wed, 12 Sep 2018 04:32:25 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 12 Sep 2018 04:32:25 GMT
WORKDIR /home/groovy
# Wed, 12 Sep 2018 04:32:32 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
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
	-	`sha256:e62df015ca0b5aa4e734cb6d6f9d4f4bb3d26934ac315e48a0c54e3af5ca39da`  
		Last Modified: Wed, 12 Sep 2018 04:39:44 GMT  
		Size: 29.8 MB (29830448 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0426fcc5fd1ba37cae5c981b3e1c18f70b887cd612be92d927071cfda0411dd`  
		Last Modified: Wed, 12 Sep 2018 04:39:41 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk-alpine` - linux; arm variant v6

```console
$ docker pull groovy@sha256:b6ac40a3fa5f554b947b39dd69222fe452a0dff583020bd8c4388493cd5052ee
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.1 MB (100054322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ccdde39c338ab8ec83b25fd2b368ea318e1c6ef498b0491f1ad51e631ee7238a`
-	Default Command: `["groovysh"]`

```dockerfile
# Wed, 12 Sep 2018 07:49:40 GMT
ADD file:9c713f2312a88f19529816851673353155f329a4b024d62b03f656b0ce32f2a6 in / 
# Wed, 12 Sep 2018 07:49:40 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 12 Sep 2018 07:49:40 GMT
CMD ["/bin/sh"]
# Wed, 12 Sep 2018 08:28:56 GMT
ENV LANG=C.UTF-8
# Wed, 12 Sep 2018 08:28:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 12 Sep 2018 08:28:57 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 12 Sep 2018 08:28:57 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 12 Sep 2018 08:28:58 GMT
ENV JAVA_VERSION=8u171
# Wed, 12 Sep 2018 08:28:58 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 12 Sep 2018 08:29:03 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 12 Sep 2018 08:49:08 GMT
CMD ["groovysh"]
# Wed, 12 Sep 2018 08:49:08 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 12 Sep 2018 08:49:08 GMT
ENV GROOVY_VERSION=2.5.2
# Sat, 15 Sep 2018 08:05:39 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Sat, 15 Sep 2018 08:05:40 GMT
USER [groovy]
# Sat, 15 Sep 2018 08:05:40 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Sat, 15 Sep 2018 08:05:41 GMT
WORKDIR /home/groovy
# Sat, 15 Sep 2018 08:05:46 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:905674ea9d9448b14f15ae82e3c34138680bac1ef4fc29088aae8c9639b502fe`  
		Last Modified: Wed, 12 Sep 2018 07:50:09 GMT  
		Size: 2.1 MB (2146453 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d91fe322e1690c8fb3f2b684fd85335d36a45e509b1568683232aede6d8a5e2b`  
		Last Modified: Wed, 12 Sep 2018 07:50:09 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5330a9c830688a5533553fc6f68b39796b550d1e9e2adec9da6321849c3091f`  
		Last Modified: Wed, 12 Sep 2018 08:30:15 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbc6a0cf1612b2dfd88775d4b635d04fe6b99bc3fdb4b25d28f1aa1244bf0a9a`  
		Last Modified: Wed, 12 Sep 2018 08:30:30 GMT  
		Size: 68.1 MB (68076599 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbd3364fead4b1d928914425cef5de6ba92d7635bc8f83f7ddf9c0063fa69f84`  
		Last Modified: Sat, 15 Sep 2018 08:09:49 GMT  
		Size: 29.8 MB (29830685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea2976063ab0bd8f71ba14975d26802fa4d8f4e04802d451204906d657783f17`  
		Last Modified: Sat, 15 Sep 2018 08:09:44 GMT  
		Size: 174.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk-alpine` - linux; arm64 variant v8

```console
$ docker pull groovy@sha256:80d617e3d01e288f15de3349b6887dfe9deadb79cc0798407c65f1caa2ed3526
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.0 MB (101046677 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:386404e3ebd988093e0718a52a547446e5e9c682e2aaa28c9d4bd1f8e9cfae02`
-	Default Command: `["groovysh"]`

```dockerfile
# Wed, 12 Sep 2018 08:42:24 GMT
ADD file:a4b53e2a2e207c5107a76c16d91b99cb1ed4ecb90b363913798e663426137d45 in / 
# Wed, 12 Sep 2018 08:42:24 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 12 Sep 2018 08:42:25 GMT
CMD ["/bin/sh"]
# Sat, 15 Sep 2018 10:31:14 GMT
ENV LANG=C.UTF-8
# Sat, 15 Sep 2018 10:31:22 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 15 Sep 2018 10:31:23 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Sat, 15 Sep 2018 10:31:24 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 15 Sep 2018 10:31:31 GMT
ENV JAVA_VERSION=8u171
# Sat, 15 Sep 2018 10:31:32 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 15 Sep 2018 10:31:44 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 15 Sep 2018 16:06:23 GMT
CMD ["groovysh"]
# Sat, 15 Sep 2018 16:06:24 GMT
ENV GROOVY_HOME=/opt/groovy
# Sat, 15 Sep 2018 16:06:25 GMT
ENV GROOVY_VERSION=2.5.2
# Sat, 15 Sep 2018 16:06:42 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Sat, 15 Sep 2018 16:06:43 GMT
USER [groovy]
# Sat, 15 Sep 2018 16:06:44 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Sat, 15 Sep 2018 16:06:45 GMT
WORKDIR /home/groovy
# Sat, 15 Sep 2018 16:06:52 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:9941776d74c9129fd585b6f0434ba48bd3a7112d6736bc02e6d12f41153cab26`  
		Last Modified: Wed, 12 Sep 2018 08:44:55 GMT  
		Size: 2.1 MB (2099762 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae94b3cb7a1b2cef0ceffe3303cd03f83434d283aab43389e586b42bea00b358`  
		Last Modified: Wed, 12 Sep 2018 08:44:55 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6f5ccd8840b9ed31daf1700ec6ed07458ba25d6734206c6c4c5910f09d8c0a6`  
		Last Modified: Sat, 15 Sep 2018 10:49:34 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0856fc6892ba80b6fab7480110b6913ba927962fc8c40602db9f56d51413c941`  
		Last Modified: Sat, 15 Sep 2018 10:49:57 GMT  
		Size: 69.1 MB (69115871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e27bad30362b5da8826278a4990c0e12e305edb6487b3f5712f3a8b94baaa9f`  
		Last Modified: Sat, 15 Sep 2018 16:17:07 GMT  
		Size: 29.8 MB (29830489 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:789a7f74c6b4e0e03210255afe70ee0f3b11d670abf7bfa918f4280442227ed1`  
		Last Modified: Sat, 15 Sep 2018 16:16:58 GMT  
		Size: 141.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk-alpine` - linux; 386

```console
$ docker pull groovy@sha256:e1956ebd41a20fa815212e2e3c327e76809d9c732f5468ea79b35b5f77b5fae4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.3 MB (103312695 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:97668d598df45777ba4dd9b95206d43b50e3ced98ddc956bd88b3e469a97d307`
-	Default Command: `["groovysh"]`

```dockerfile
# Wed, 12 Sep 2018 10:38:54 GMT
ADD file:b789aca08d6985c0bf373a2ca5f2a263d45e3a789aa6bbcd1fe1d47133f985d2 in / 
# Wed, 12 Sep 2018 10:38:54 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 12 Sep 2018 10:38:54 GMT
CMD ["/bin/sh"]
# Wed, 12 Sep 2018 12:26:37 GMT
ENV LANG=C.UTF-8
# Wed, 12 Sep 2018 12:26:38 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 12 Sep 2018 12:26:38 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 12 Sep 2018 12:26:38 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 12 Sep 2018 12:26:38 GMT
ENV JAVA_VERSION=8u171
# Wed, 12 Sep 2018 12:26:39 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 12 Sep 2018 12:26:43 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 12 Sep 2018 18:05:05 GMT
CMD ["groovysh"]
# Wed, 12 Sep 2018 18:05:06 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 12 Sep 2018 18:05:06 GMT
ENV GROOVY_VERSION=2.5.2
# Wed, 12 Sep 2018 18:05:14 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 12 Sep 2018 18:05:15 GMT
USER [groovy]
# Wed, 12 Sep 2018 18:05:15 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 12 Sep 2018 18:05:15 GMT
WORKDIR /home/groovy
# Wed, 12 Sep 2018 18:05:17 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:6b5c2e9bbf9885ccefe772a5a1f471d7da4315b7bf43ec3b4c014a65d04073b1`  
		Last Modified: Wed, 12 Sep 2018 10:39:28 GMT  
		Size: 2.3 MB (2271460 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4d99e807699886f28203b3284584d7b093a61a84c40230f7094513bb2f84cd2`  
		Last Modified: Wed, 12 Sep 2018 10:39:28 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28e11b9507e2b27f5ba6cf1ca7a6129f7238ae95981ee1dce74b023e8fea1d68`  
		Last Modified: Wed, 12 Sep 2018 12:28:14 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18c44e31b3fde843ce77451a9d3432fecef5208c345c56937b36b3626b930550`  
		Last Modified: Wed, 12 Sep 2018 12:28:23 GMT  
		Size: 71.2 MB (71210069 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:082a52087901988a1a8d87bc3904a4f97f6c2e13d14a886e481599ce1dafd681`  
		Last Modified: Wed, 12 Sep 2018 18:09:54 GMT  
		Size: 29.8 MB (29830612 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:624f5321c3f82cebce711b7bcefa3d5a9dee58267df84cde50643ed30bc44171`  
		Last Modified: Wed, 12 Sep 2018 18:09:49 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk-alpine` - linux; ppc64le

```console
$ docker pull groovy@sha256:60de71ff8b5dfcdbe4f99f021d364f23129337dd1856be098b88ef3f70e5aec0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.8 MB (101783124 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e5a52b69fb215676894f93576e78679d03aa6a6669c3a9ed04003b438a99c159`
-	Default Command: `["groovysh"]`

```dockerfile
# Wed, 12 Sep 2018 08:18:11 GMT
ADD file:0991fe2a00b8319ade0b97ea20b79708b45153da36419ca58378c8bece0f987c in / 
# Wed, 12 Sep 2018 08:18:13 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 12 Sep 2018 08:18:14 GMT
CMD ["/bin/sh"]
# Wed, 12 Sep 2018 10:42:47 GMT
ENV LANG=C.UTF-8
# Wed, 12 Sep 2018 10:42:49 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 12 Sep 2018 10:42:50 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 12 Sep 2018 10:42:50 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 12 Sep 2018 10:42:51 GMT
ENV JAVA_VERSION=8u171
# Wed, 12 Sep 2018 10:42:52 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 12 Sep 2018 10:43:03 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 12 Sep 2018 14:38:43 GMT
CMD ["groovysh"]
# Wed, 12 Sep 2018 14:38:45 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 12 Sep 2018 14:38:47 GMT
ENV GROOVY_VERSION=2.5.2
# Wed, 12 Sep 2018 14:39:09 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 12 Sep 2018 14:39:10 GMT
USER [groovy]
# Wed, 12 Sep 2018 14:39:11 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 12 Sep 2018 14:39:12 GMT
WORKDIR /home/groovy
# Wed, 12 Sep 2018 14:39:18 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:d6201b52ea9b908d4d6e950e2a79ded27be48979d6f0f63bd3a57b16b621f188`  
		Last Modified: Wed, 12 Sep 2018 08:19:46 GMT  
		Size: 2.2 MB (2195226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c5cedde51de1c8ffccd5521fd02fc1efc1cc44ece2d5dccb1e550a65366cd80`  
		Last Modified: Wed, 12 Sep 2018 08:19:44 GMT  
		Size: 177.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a54bbb0272d84bd92ba5131b652f8b30f8a037eb25502b09336b9879057a5b41`  
		Last Modified: Wed, 12 Sep 2018 10:45:39 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de69629a94cc7adfc02c94bb5764387c5b3132ed0500a6c07b2048d7d09deb3f`  
		Last Modified: Wed, 12 Sep 2018 10:45:50 GMT  
		Size: 69.8 MB (69756665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff0974c45bc5bbb6f2cc0aaa0834162939dbf4231c71fa38033a48b555d761df`  
		Last Modified: Wed, 12 Sep 2018 14:52:21 GMT  
		Size: 29.8 MB (29830645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:060dede98ea3a2fbcbb77e67699eaa5dda01c398b58e6db72f3c322a29f76a22`  
		Last Modified: Wed, 12 Sep 2018 14:52:17 GMT  
		Size: 173.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk-alpine` - linux; s390x

```console
$ docker pull groovy@sha256:71fa73fea32355de2842598b90e6c84a506562205aa9739dcac4368a9fc33f64
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.5 MB (101520496 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fad2b2be98f1b04ca22b04f5e6030608584a7913958c5d8060fc0582f0d0052f`
-	Default Command: `["groovysh"]`

```dockerfile
# Wed, 12 Sep 2018 11:42:25 GMT
ADD file:532f451315fcf5c4077ef91f62d9838cf5681b4a348af2d78f6edd825146612c in / 
# Wed, 12 Sep 2018 11:42:25 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 12 Sep 2018 11:42:25 GMT
CMD ["/bin/sh"]
# Wed, 12 Sep 2018 13:14:33 GMT
ENV LANG=C.UTF-8
# Wed, 12 Sep 2018 13:14:33 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 12 Sep 2018 13:14:33 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 12 Sep 2018 13:14:34 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 12 Sep 2018 13:14:34 GMT
ENV JAVA_VERSION=8u171
# Wed, 12 Sep 2018 13:14:34 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 12 Sep 2018 13:14:37 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 12 Sep 2018 14:08:51 GMT
CMD ["groovysh"]
# Wed, 12 Sep 2018 14:08:51 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 12 Sep 2018 14:08:51 GMT
ENV GROOVY_VERSION=2.5.2
# Wed, 12 Sep 2018 14:08:58 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 12 Sep 2018 14:09:01 GMT
USER [groovy]
# Wed, 12 Sep 2018 14:09:02 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 12 Sep 2018 14:09:02 GMT
WORKDIR /home/groovy
# Wed, 12 Sep 2018 14:09:04 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:e5d7a290acc264d66e5c29923d4b8a79135ffd15887225581968bf7df22fb281`  
		Last Modified: Wed, 12 Sep 2018 11:43:25 GMT  
		Size: 2.3 MB (2307746 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad01149bcd3bd207c03ab0c38897be9653222644a37b651c399c24f1e9170313`  
		Last Modified: Wed, 12 Sep 2018 11:43:24 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d467c81155dfdb8e21d7a7abb5210cdfe51c5e8336b7a58bf0fecf06d36633e`  
		Last Modified: Wed, 12 Sep 2018 13:16:20 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5076f0b2ce57a9a8b84d1be529d601310aab2edcd0146ea5571c32c8b4c338b4`  
		Last Modified: Wed, 12 Sep 2018 13:16:27 GMT  
		Size: 69.4 MB (69381652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f1449dd2dddeade71da4fd1fce47cd34f4771ea0b979c006d72c8be0ea0c9ff`  
		Last Modified: Wed, 12 Sep 2018 14:15:36 GMT  
		Size: 29.8 MB (29830543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:873dc137c77ff60a6ca8dc8a347a731ba03e8df17faec6192675448c53fd738e`  
		Last Modified: Wed, 12 Sep 2018 14:15:31 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
