## `mysql:latest`

```console
$ docker pull mysql@sha256:038f5f6ea8c8f63cfce1bce9c057ab3691cad867e18da8ad4ba6c90874d0537a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mysql:latest` - linux; amd64

```console
$ docker pull mysql@sha256:59e5ff6c9d6177d4b98432d055233502451da5c32c3481055b41942785df9e77
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **137.7 MB (137704235 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a834f03bd02bb88cdbe0e289b9cd6056f1d42fa94792c524b4fddc474dab628`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:34 GMT
ADD file:e6ca98733431f75e97eb09758ba64065d213d51bd2070a95cf15f2ff5adccfc4 in / 
# Tue, 04 Sep 2018 21:21:34 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 00:37:20 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Wed, 05 Sep 2018 00:37:26 GMT
RUN apt-get update && apt-get install -y --no-install-recommends gnupg dirmngr && rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 00:37:27 GMT
ENV GOSU_VERSION=1.7
# Wed, 05 Sep 2018 00:37:38 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& gpgconf --kill all 	&& rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Wed, 05 Sep 2018 00:37:38 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 05 Sep 2018 00:37:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		pwgen 		openssl 		perl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 00:37:52 GMT
RUN set -ex; 	key='A4A9406876FCBD3C456770C88C718D3B5072E1F5'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/mysql.gpg; 	gpgconf --kill all; 	rm -rf "$GNUPGHOME"; 	apt-key list > /dev/null
# Wed, 05 Sep 2018 00:37:52 GMT
ENV MYSQL_MAJOR=8.0
# Wed, 05 Sep 2018 00:37:52 GMT
ENV MYSQL_VERSION=8.0.12-1debian9
# Wed, 05 Sep 2018 00:37:53 GMT
RUN echo "deb http://repo.mysql.com/apt/debian/ stretch mysql-${MYSQL_MAJOR}" > /etc/apt/sources.list.d/mysql.list
# Wed, 05 Sep 2018 00:38:23 GMT
RUN { 		echo mysql-community-server mysql-community-server/data-dir select ''; 		echo mysql-community-server mysql-community-server/root-pass password ''; 		echo mysql-community-server mysql-community-server/re-root-pass password ''; 		echo mysql-community-server mysql-community-server/remove-test-db select false; 	} | debconf-set-selections 	&& apt-get update && apt-get install -y mysql-community-client="${MYSQL_VERSION}" mysql-community-server-core="${MYSQL_VERSION}" && rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Wed, 05 Sep 2018 00:38:23 GMT
VOLUME [/var/lib/mysql]
# Wed, 05 Sep 2018 00:38:24 GMT
COPY dir:110dcf1221c1f9432c68c32a2465ef0b40994f401d5fae0b0de80025bcf839a5 in /etc/mysql/ 
# Wed, 05 Sep 2018 00:38:24 GMT
COPY file:59647006b032bcb29e59fba419c45f9d14154b34df99013c41321e204048254c in /usr/local/bin/ 
# Wed, 05 Sep 2018 00:38:25 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Wed, 05 Sep 2018 00:38:25 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 05 Sep 2018 00:38:25 GMT
EXPOSE 3306/tcp 33060/tcp
# Wed, 05 Sep 2018 00:38:25 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:802b00ed6f79f48e6a5f44ecbcaf43563d6077aaecb565eee1dfc615c0b18c00`  
		Last Modified: Tue, 04 Sep 2018 21:25:45 GMT  
		Size: 22.5 MB (22485965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30f19a05b898876bcbed44d787394bf2655c34aa3334e5c5d33f213856ff3585`  
		Last Modified: Wed, 05 Sep 2018 00:41:08 GMT  
		Size: 1.7 KB (1741 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e43303be5e9eed187054f5d19ebfa02dec19dfa1a83ed6d88a69a588bc840a9`  
		Last Modified: Wed, 05 Sep 2018 00:41:09 GMT  
		Size: 4.5 MB (4498543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94b281824ae27d4ba5d8f09da927c173ff8912becbc23fccef8a690bc00b5c8e`  
		Last Modified: Wed, 05 Sep 2018 00:41:07 GMT  
		Size: 1.3 MB (1270276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51eb397095b112a5047d725805bef05b7a1430617dc4b96afc56355e93e22633`  
		Last Modified: Wed, 05 Sep 2018 00:41:07 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54567da6fdf0f9cc014f42de0d4c3398f5b22f913eed36937dd7f8ca7ea94119`  
		Last Modified: Wed, 05 Sep 2018 00:41:10 GMT  
		Size: 12.1 MB (12091217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc57ddb85cceb38937031945bdd7d7e4cbae5ba2c3dd5598ad4a96a137cb5ee0`  
		Last Modified: Wed, 05 Sep 2018 00:41:07 GMT  
		Size: 23.2 KB (23203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6cd3c7302aa455ce5db582420f8a4405dd83a354f7d617374e26e2b0a86475d`  
		Last Modified: Wed, 05 Sep 2018 00:41:05 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8263dad8dbbfe5edf5187ef7e2a2054d59ef9d72bc019f4202467bc172e03ef`  
		Last Modified: Wed, 05 Sep 2018 00:41:34 GMT  
		Size: 97.3 MB (97328992 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:780f2f86056d502f924362510001e15fe055edb14b0eac4e8e64b6f249cc8345`  
		Last Modified: Wed, 05 Sep 2018 00:41:05 GMT  
		Size: 893.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e0761cb58cd15e8a315acb895c609786ef640b8fdd773e061f94b69759ae13c`  
		Last Modified: Wed, 05 Sep 2018 00:41:05 GMT  
		Size: 2.9 KB (2946 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7588cfc269e5e71903a9c75dcb126366f1c04e6d26d0db5636a6a747f9303789`  
		Last Modified: Wed, 05 Sep 2018 00:41:05 GMT  
		Size: 118.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
