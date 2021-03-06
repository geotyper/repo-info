## `rabbitmq:3-management`

```console
$ docker pull rabbitmq@sha256:cde86470875ff1dde979041ad43153cfa0e1d47241e57fcad54a8ab8ed958da0
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

### `rabbitmq:3-management` - linux; amd64

```console
$ docker pull rabbitmq@sha256:4a8179df47a2296104d168a75be033de028b41e3e4c8ba973dfbd1dc1c458464
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **73.4 MB (73413278 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:75472a5c510b61464a1791eaa76edf71080d5f9208388f0e018fdd79582330c3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:34 GMT
ADD file:e6ca98733431f75e97eb09758ba64065d213d51bd2070a95cf15f2ff5adccfc4 in / 
# Tue, 04 Sep 2018 21:21:34 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 05:21:01 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 05:21:02 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 05 Sep 2018 05:21:02 GMT
ENV GOSU_VERSION=1.10
# Wed, 05 Sep 2018 05:21:13 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 05 Sep 2018 05:21:14 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 05 Sep 2018 05:21:38 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 05:21:38 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 05 Sep 2018 05:21:38 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 05:21:39 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Fri, 21 Sep 2018 19:20:23 GMT
ENV RABBITMQ_VERSION=3.7.8
# Fri, 21 Sep 2018 19:20:23 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Fri, 21 Sep 2018 19:20:23 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Fri, 21 Sep 2018 19:20:44 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Fri, 21 Sep 2018 19:20:44 GMT
ENV LANG=C.UTF-8
# Fri, 21 Sep 2018 19:20:44 GMT
ENV HOME=/var/lib/rabbitmq
# Fri, 21 Sep 2018 19:20:45 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Fri, 21 Sep 2018 19:20:45 GMT
VOLUME [/var/lib/rabbitmq]
# Fri, 21 Sep 2018 19:20:46 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Fri, 21 Sep 2018 19:20:47 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Fri, 21 Sep 2018 19:20:47 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Fri, 21 Sep 2018 19:20:48 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 21 Sep 2018 19:20:48 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 21 Sep 2018 19:20:48 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 21 Sep 2018 19:20:49 GMT
CMD ["rabbitmq-server"]
# Fri, 21 Sep 2018 19:21:07 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Fri, 21 Sep 2018 19:21:18 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Fri, 21 Sep 2018 19:21:19 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:802b00ed6f79f48e6a5f44ecbcaf43563d6077aaecb565eee1dfc615c0b18c00`  
		Last Modified: Tue, 04 Sep 2018 21:25:45 GMT  
		Size: 22.5 MB (22485965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84fe35f04ebea261787064fcf29714d8a188578fd3aae88a1672366b5243a1b4`  
		Last Modified: Wed, 05 Sep 2018 05:24:51 GMT  
		Size: 4.5 MB (4498555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72a118dc68c2e54abc54162dd19892c08a71709d7499eabe7f6ac95205c2494f`  
		Last Modified: Wed, 05 Sep 2018 05:24:50 GMT  
		Size: 4.1 KB (4071 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51c19971869789806dbf507bf25ba148decd6223ec7dcf5621f7555ebb9fcd41`  
		Last Modified: Wed, 05 Sep 2018 05:24:50 GMT  
		Size: 951.9 KB (951900 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e74b797281ea162830289012ea83cfe1e59f93ac0f85f76ad9386dd41305fd30`  
		Last Modified: Wed, 05 Sep 2018 05:24:49 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2b0494f0e3c744f09fd327476571006c12f9f6cfc048f97f2c9e6c66999db94`  
		Last Modified: Wed, 05 Sep 2018 05:24:52 GMT  
		Size: 27.5 MB (27500750 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d980114df034ef4993a83465524fafa7344b25e19528982353c9cf74bf5f55a`  
		Last Modified: Fri, 21 Sep 2018 19:22:19 GMT  
		Size: 10.3 MB (10341393 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04ca5fedb825835294e2565cc58d227196127ecc0edc0c281346b26197bc100f`  
		Last Modified: Fri, 21 Sep 2018 19:22:17 GMT  
		Size: 2.3 KB (2261 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec1e615d6da0531fe7024d2a969229da3883db973c818a56c5d6a400c3a5c271`  
		Last Modified: Fri, 21 Sep 2018 19:22:17 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e9a78cfa9a669c16e12c1a9ac682402319955e856326ec083e07081a19b0b25`  
		Last Modified: Fri, 21 Sep 2018 19:22:17 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6dad79c7b8b87e34a5e1daaf7feb10cbad88e100db107941e83f8794fb278cc`  
		Last Modified: Fri, 21 Sep 2018 19:22:18 GMT  
		Size: 4.2 KB (4182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81bf45b8fd5229e3afde232d882b510fe05c8cdafb7a601bbb654e3f54767b8a`  
		Last Modified: Fri, 21 Sep 2018 19:22:18 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f290272ddb5f56456b3882a4b2b6f93b851b92c8e7433e7d27489aa99700fd53`  
		Last Modified: Fri, 21 Sep 2018 19:23:17 GMT  
		Size: 193.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:191f528c58708d2416177b680923c69beb1685c0f2c73d7fe0f801c204e420b5`  
		Last Modified: Fri, 21 Sep 2018 19:23:19 GMT  
		Size: 7.6 MB (7623256 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; arm variant v5

```console
$ docker pull rabbitmq@sha256:f5303690765cafcf06bf200bc88d91988206cf31fe1dfb965c45cac5ab2b1313
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **69.1 MB (69120818 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4e3caa41d04ab4619888b24becf69c21faf9a9447ca8eb6456741b24c98e1f64`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Wed, 05 Sep 2018 08:55:26 GMT
ADD file:589b238a5fdfe8cc752d0f1769d0c392a7ac3d1204f9247c4eea21dd805663b0 in / 
# Wed, 05 Sep 2018 08:55:26 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 11:45:00 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 11:45:01 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 05 Sep 2018 11:45:01 GMT
ENV GOSU_VERSION=1.10
# Wed, 05 Sep 2018 11:45:20 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 05 Sep 2018 11:45:21 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 05 Sep 2018 11:46:06 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 11:46:07 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 05 Sep 2018 11:46:07 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 11:46:08 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Sat, 22 Sep 2018 08:58:03 GMT
ENV RABBITMQ_VERSION=3.7.8
# Sat, 22 Sep 2018 08:58:03 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Sat, 22 Sep 2018 08:58:04 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Sat, 22 Sep 2018 08:58:43 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Sat, 22 Sep 2018 08:58:44 GMT
ENV LANG=C.UTF-8
# Sat, 22 Sep 2018 08:58:44 GMT
ENV HOME=/var/lib/rabbitmq
# Sat, 22 Sep 2018 08:58:45 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Sat, 22 Sep 2018 08:58:46 GMT
VOLUME [/var/lib/rabbitmq]
# Sat, 22 Sep 2018 08:58:47 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Sat, 22 Sep 2018 08:58:48 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Sat, 22 Sep 2018 08:58:49 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Sat, 22 Sep 2018 08:58:50 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 22 Sep 2018 08:58:51 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 22 Sep 2018 08:58:52 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 22 Sep 2018 08:58:52 GMT
CMD ["rabbitmq-server"]
# Sat, 22 Sep 2018 08:59:10 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 22 Sep 2018 08:59:32 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Sat, 22 Sep 2018 08:59:32 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:675207fbfe2baab74b37fd78c8be6e05579c046e848f9e9762e048899fa484f1`  
		Last Modified: Wed, 05 Sep 2018 09:04:43 GMT  
		Size: 21.2 MB (21162872 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:483021b9c38437adcd233ec231bbe3d5f2262264fdb2cfdd6040e28622abfeed`  
		Last Modified: Wed, 05 Sep 2018 11:49:48 GMT  
		Size: 4.2 MB (4231636 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0de799b221ef6d17d523a8146fae2f4c5b756afa8dbcde3436ebe67d2cfb3760`  
		Last Modified: Wed, 05 Sep 2018 11:49:46 GMT  
		Size: 4.1 KB (4086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23e2b5ada6e33dc5ae042bd4ae10d7d2e5cef590482f162b4fc967c577be9776`  
		Last Modified: Wed, 05 Sep 2018 11:49:45 GMT  
		Size: 942.3 KB (942332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65428a380acc7019931c23005421c6f7eacc5c73ae5a77a6340977af268cdb29`  
		Last Modified: Wed, 05 Sep 2018 11:49:45 GMT  
		Size: 358.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb4f4592eb0138d0e1a977e797f6b1b1861414b013b17251558a55338917b431`  
		Last Modified: Wed, 05 Sep 2018 11:49:50 GMT  
		Size: 25.0 MB (24988439 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9a36e2eac1d50e768d2e155c3fa6eb8e7ed70d329f075619ed2eedb3ce65da4`  
		Last Modified: Sat, 22 Sep 2018 09:00:04 GMT  
		Size: 10.3 MB (10310410 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2eb90657b133110385ab6178da97ba097dc953c4db394ffff1370ef7f0b39b59`  
		Last Modified: Sat, 22 Sep 2018 09:00:01 GMT  
		Size: 2.3 KB (2258 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d42d8ba2e5a411d9a0e012ae3d4b234f938de9cbba8993655cd48317a78d8108`  
		Last Modified: Sat, 22 Sep 2018 09:00:01 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9767a7551c4b2ee7f7101af8e55721ce83af6c18e25606d15095e146108ad04a`  
		Last Modified: Sat, 22 Sep 2018 09:00:01 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:859bd681e58f37404c3814d419985804f6fd270b5f056d568fce48e2e1d6ffbd`  
		Last Modified: Sat, 22 Sep 2018 09:00:01 GMT  
		Size: 4.2 KB (4183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a722bdd44282ba09454c487b7c111669310847853a6f817ec1e002625cf1ead`  
		Last Modified: Sat, 22 Sep 2018 09:00:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a1332ceb5af448fbb61f0e5ce04fea17c7c697fd68be085cc67659a41239577`  
		Last Modified: Sat, 22 Sep 2018 09:00:48 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:563761b3da829e663850b495b9c438bd60379087eb4174f51fd39ce5588a4f8a`  
		Last Modified: Sat, 22 Sep 2018 09:00:51 GMT  
		Size: 7.5 MB (7473660 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; arm variant v7

```console
$ docker pull rabbitmq@sha256:3d9dd1aef88e74afeeb7e63d894df78666f55c8cca59dd2daf1f86315e770da0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **66.2 MB (66219145 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1ce62b77ecb087164ebc1e4b88b9b81ce14193ceeb65f2dcdaf4cd24d4bee3af`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Wed, 05 Sep 2018 12:04:38 GMT
ADD file:d20313e46e6d5f092327691d5bc0e83ad6b16d7b44a8dc82fa973c25a13257e7 in / 
# Wed, 05 Sep 2018 12:04:38 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 15:47:26 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 15:47:28 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 05 Sep 2018 15:47:28 GMT
ENV GOSU_VERSION=1.10
# Wed, 05 Sep 2018 15:47:43 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 05 Sep 2018 15:47:44 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 05 Sep 2018 15:48:21 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 15:48:21 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 05 Sep 2018 15:48:21 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 15:48:22 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Sat, 22 Sep 2018 11:57:54 GMT
ENV RABBITMQ_VERSION=3.7.8
# Sat, 22 Sep 2018 11:57:54 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Sat, 22 Sep 2018 11:57:55 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Sat, 22 Sep 2018 11:58:28 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Sat, 22 Sep 2018 11:58:28 GMT
ENV LANG=C.UTF-8
# Sat, 22 Sep 2018 11:58:29 GMT
ENV HOME=/var/lib/rabbitmq
# Sat, 22 Sep 2018 11:58:30 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Sat, 22 Sep 2018 11:58:31 GMT
VOLUME [/var/lib/rabbitmq]
# Sat, 22 Sep 2018 11:58:33 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Sat, 22 Sep 2018 11:58:35 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Sat, 22 Sep 2018 11:58:36 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Sat, 22 Sep 2018 11:58:37 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 22 Sep 2018 11:58:38 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 22 Sep 2018 11:58:38 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 22 Sep 2018 11:58:39 GMT
CMD ["rabbitmq-server"]
# Sat, 22 Sep 2018 11:59:01 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 22 Sep 2018 11:59:20 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Sat, 22 Sep 2018 11:59:20 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:2e5bbd238113a2057012dfb78ac9665531c276c48962d208492c8802fb0503c0`  
		Last Modified: Wed, 05 Sep 2018 12:13:41 GMT  
		Size: 19.3 MB (19270166 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5141246d136f294078d95e58ccfe7ad4e4cb36e3f326facc50866aa09e2b87b`  
		Last Modified: Wed, 05 Sep 2018 15:51:43 GMT  
		Size: 3.9 MB (3868671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b31f084a36199cdd4d59bd6189376f7eaf477a8bef7fef0eba52f25fae320a9f`  
		Last Modified: Wed, 05 Sep 2018 15:51:42 GMT  
		Size: 4.1 KB (4084 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db8fd793fb8cf44bd0327de96340e9367b4baaabaad4e35d2f36080d8b6ea5e9`  
		Last Modified: Wed, 05 Sep 2018 15:51:43 GMT  
		Size: 926.0 KB (926006 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa6e051a0c0939154b197018729fb29d5214cbd482da85ed4fd1631a20f4308f`  
		Last Modified: Wed, 05 Sep 2018 15:51:41 GMT  
		Size: 357.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32acc40aae41518db9bf3704cd74f629ec1af9cbd9a2d44996263363ea581c6f`  
		Last Modified: Wed, 05 Sep 2018 15:51:45 GMT  
		Size: 24.7 MB (24677064 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71718005867114805163fcfcc9cfdea214c1e568f705f61b7d2429ef23fa12cb`  
		Last Modified: Sat, 22 Sep 2018 11:59:49 GMT  
		Size: 10.3 MB (10282559 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4125509782940891f96aaa3cf061f4dd59470f7116637d9eaf29ac94e295a1d`  
		Last Modified: Sat, 22 Sep 2018 11:59:46 GMT  
		Size: 2.3 KB (2263 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964d5124ffe1ca710126efdbcfc115c8d4c7ef57e0a4d371a8b982a8d501bd8c`  
		Last Modified: Sat, 22 Sep 2018 11:59:46 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5dc492e42909ea18ee5f52c6a6a15db1a13587105a2b67ead3c10efabb1a598`  
		Last Modified: Sat, 22 Sep 2018 11:59:46 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2b2e171826b2eeacf977f847039dbfef64d5c816d825101422bad10a9bafe4e`  
		Last Modified: Sat, 22 Sep 2018 11:59:46 GMT  
		Size: 4.2 KB (4180 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9bed37d9b6fe7f4af1d635ff683ca5daa6f73978f5759c102f7861f14cdfa097`  
		Last Modified: Sat, 22 Sep 2018 11:59:46 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c5450483a95b070111be81803a56e214f1438a5fda350032cfcd61982b0093b`  
		Last Modified: Sat, 22 Sep 2018 12:00:32 GMT  
		Size: 192.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d0b7005646f965608e94a28848f0536d72537e0509532ebd1030adb500d76f6`  
		Last Modified: Sat, 22 Sep 2018 12:00:34 GMT  
		Size: 7.2 MB (7183210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; arm64 variant v8

```console
$ docker pull rabbitmq@sha256:431e006e72d705dd7c4f127028311a1b1599df350afde3ea6a2650931599d4c8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **68.2 MB (68164651 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c555744928dd03693e679a134f4f32e7f982349fa1593718669cadcca2ccf9b0`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Wed, 05 Sep 2018 08:51:48 GMT
ADD file:11982f247d3c0dc005ade5290cf65e3e0f9d4a64f141d4d63317af8680ef094a in / 
# Wed, 05 Sep 2018 08:52:05 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 17:59:48 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 17:59:52 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 05 Sep 2018 17:59:53 GMT
ENV GOSU_VERSION=1.10
# Wed, 05 Sep 2018 18:01:08 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 05 Sep 2018 18:01:10 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 05 Sep 2018 18:02:48 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 18:02:48 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 05 Sep 2018 18:02:49 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 18:02:50 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Sat, 22 Sep 2018 08:51:38 GMT
ENV RABBITMQ_VERSION=3.7.8
# Sat, 22 Sep 2018 08:51:47 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Sat, 22 Sep 2018 08:51:48 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Sat, 22 Sep 2018 08:52:43 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Sat, 22 Sep 2018 08:52:49 GMT
ENV LANG=C.UTF-8
# Sat, 22 Sep 2018 08:52:49 GMT
ENV HOME=/var/lib/rabbitmq
# Sat, 22 Sep 2018 08:52:51 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Sat, 22 Sep 2018 08:52:52 GMT
VOLUME [/var/lib/rabbitmq]
# Sat, 22 Sep 2018 08:53:03 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Sat, 22 Sep 2018 08:53:04 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Sat, 22 Sep 2018 08:53:14 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Sat, 22 Sep 2018 08:53:16 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 22 Sep 2018 08:53:17 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 22 Sep 2018 08:53:26 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 22 Sep 2018 08:53:27 GMT
CMD ["rabbitmq-server"]
# Sat, 22 Sep 2018 08:54:01 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 22 Sep 2018 08:54:37 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Sat, 22 Sep 2018 08:54:38 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:8d586fc7919319b234c6d8676e8dc3baa39e4edf195a2dec935bdaeeb0862163`  
		Last Modified: Wed, 05 Sep 2018 09:09:38 GMT  
		Size: 20.3 MB (20331641 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e3e37db5cf675e4afee42d261d405850f9661011376c9e32dcf161b994b5784`  
		Last Modified: Wed, 05 Sep 2018 18:10:27 GMT  
		Size: 4.1 MB (4073269 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a489138492c1c3398d5e832adb250d71806f6d1c1ee77f0d4386d242770e4f5`  
		Last Modified: Wed, 05 Sep 2018 18:10:25 GMT  
		Size: 4.1 KB (4083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a786d0df6cef56007fb33342e229dc469e545f3fbd266b4b427d1fcd6f265084`  
		Last Modified: Wed, 05 Sep 2018 18:10:25 GMT  
		Size: 919.2 KB (919245 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d8290a5f844dc24fafb21b0cc2eefa710b721caab388788f0f84fb6c5304125`  
		Last Modified: Wed, 05 Sep 2018 18:10:24 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dacda0a12c7cb0992a5d95f75099782e66e2f4561cfa697f95a32df5c592bc68`  
		Last Modified: Wed, 05 Sep 2018 18:10:30 GMT  
		Size: 25.0 MB (25045917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42cf4ae8997417961ed19100842c7e6c280e4c623403e85c0047ae7cbdfa9208`  
		Last Modified: Sat, 22 Sep 2018 08:59:14 GMT  
		Size: 10.3 MB (10307125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62359fecc08685998249d40a89ab975841f91f6d7dda13315a83d8f3c7f50ab1`  
		Last Modified: Sat, 22 Sep 2018 08:59:10 GMT  
		Size: 2.3 KB (2261 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e7d142bc95a688efcc89d03f06eb191ff71ac493a62059adbe7c8322f301fee`  
		Last Modified: Sat, 22 Sep 2018 08:59:10 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcbfe2ca2db93d20210ba636666631f84f380156d7fa7a98fe93a68cd7d9a366`  
		Last Modified: Sat, 22 Sep 2018 08:59:10 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:868ee8a3aecd0459b8894c132648bdfb8b441130ca853ba2bba585daa25e7412`  
		Last Modified: Sat, 22 Sep 2018 08:59:10 GMT  
		Size: 4.2 KB (4183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3a0ab2b1147790075787c5b2251cf77110a3da7fa083d1fd2c40e5824d0c25f2`  
		Last Modified: Sat, 22 Sep 2018 08:59:10 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0966060600a02d135bd1d95fa69313f34a18325cc3c2702f86423a290b961b2`  
		Last Modified: Sat, 22 Sep 2018 09:00:04 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4c7c4d3288ee7f0b504ceaf3a731636f036ed45255e7bf7e116e912a769f3ce`  
		Last Modified: Sat, 22 Sep 2018 09:00:06 GMT  
		Size: 7.5 MB (7475982 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; 386

```console
$ docker pull rabbitmq@sha256:4ca92fa54f3cb07f6fee0e448c28515fdbb85a431f39c92ea6c9f2d02f50364d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **74.7 MB (74657202 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:94a37c937aa51c10d2e6a0b624b748d8640bec5d50ec1a68ad31275b175f8964`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Wed, 05 Sep 2018 10:43:58 GMT
ADD file:e2998c599fe122e866e9244aa7fdb1d3bdddb454863a1d003340392684d2388d in / 
# Wed, 05 Sep 2018 10:43:59 GMT
CMD ["bash"]
# Fri, 07 Sep 2018 00:46:57 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Fri, 07 Sep 2018 00:46:57 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 07 Sep 2018 00:46:58 GMT
ENV GOSU_VERSION=1.10
# Fri, 07 Sep 2018 00:47:09 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Fri, 07 Sep 2018 00:47:10 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Fri, 07 Sep 2018 00:47:33 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Fri, 07 Sep 2018 00:47:33 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Fri, 07 Sep 2018 00:47:33 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 07 Sep 2018 00:47:33 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Sat, 22 Sep 2018 10:54:05 GMT
ENV RABBITMQ_VERSION=3.7.8
# Sat, 22 Sep 2018 10:54:05 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Sat, 22 Sep 2018 10:54:05 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Sat, 22 Sep 2018 10:54:27 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Sat, 22 Sep 2018 10:54:27 GMT
ENV LANG=C.UTF-8
# Sat, 22 Sep 2018 10:54:27 GMT
ENV HOME=/var/lib/rabbitmq
# Sat, 22 Sep 2018 10:54:28 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Sat, 22 Sep 2018 10:54:28 GMT
VOLUME [/var/lib/rabbitmq]
# Sat, 22 Sep 2018 10:54:29 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Sat, 22 Sep 2018 10:54:29 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Sat, 22 Sep 2018 10:54:30 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Sat, 22 Sep 2018 10:54:30 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 22 Sep 2018 10:54:31 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 22 Sep 2018 10:54:31 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 22 Sep 2018 10:54:31 GMT
CMD ["rabbitmq-server"]
# Sat, 22 Sep 2018 10:54:45 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 22 Sep 2018 10:54:58 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Sat, 22 Sep 2018 10:54:58 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:6a04e6fc95134a0f0b1fc5f312d7930a2abb685ce0081538c60b7d51a221cbb1`  
		Last Modified: Wed, 05 Sep 2018 10:52:19 GMT  
		Size: 23.1 MB (23126488 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3a4dae48f2c41c273519bd218a68670fd300dd05b610af53de52cbd92e018d83`  
		Last Modified: Fri, 07 Sep 2018 00:50:33 GMT  
		Size: 4.8 MB (4803829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aec4312e65d61f18a107cd8e5936a2ced8a79d49d10dc094a2e1c17d33a1810b`  
		Last Modified: Fri, 07 Sep 2018 00:50:31 GMT  
		Size: 4.1 KB (4061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:111d7d048cfd3b5609811a3f5c8139eb45fb2824715b10855d24520943ffb47d`  
		Last Modified: Fri, 07 Sep 2018 00:50:31 GMT  
		Size: 931.4 KB (931361 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6a318ff9007a5982a270089f57c8d36fcff6af7d6ed1ea9403f16bc7c601c93`  
		Last Modified: Fri, 07 Sep 2018 00:50:30 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fb792113082af215b5c986d14f711522c0e52b5e834f6f2eef5f0ef8f30eaf4`  
		Last Modified: Fri, 07 Sep 2018 00:50:35 GMT  
		Size: 27.7 MB (27706509 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3274992d0c9e2460bbed24ca406bcf79ec7487dbdf9fef188ba37a9da966ddd`  
		Last Modified: Sat, 22 Sep 2018 10:55:58 GMT  
		Size: 10.4 MB (10362559 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7a0f36c2373a121f4f6e95a736f0be36e6648c88b0beea9eb6f6ca6be243989`  
		Last Modified: Sat, 22 Sep 2018 10:55:56 GMT  
		Size: 2.3 KB (2262 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08f9a2c4186cb90349be0e729bf680a6170a064acaada8fe760aac10bf0d23cc`  
		Last Modified: Sat, 22 Sep 2018 10:55:56 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56217ffada6f4deb2ad7ef790e07dd8042b160fb7ae80bede2ac6b6d6e0650e1`  
		Last Modified: Sat, 22 Sep 2018 10:55:56 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f64b3d065ae8fd30da979712a0b6c1efa0a4688b6350aac755e2110a8dc24fab`  
		Last Modified: Sat, 22 Sep 2018 10:55:56 GMT  
		Size: 4.2 KB (4183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44a9c4cadf11e3ca02871084a456f83c1a1c2f7802412edfea0a6885de5f9363`  
		Last Modified: Sat, 22 Sep 2018 10:55:56 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8443fa238831c31b891a7cc2b48dac1a4c5f33d210db2b5094ef7ed369810af`  
		Last Modified: Sat, 22 Sep 2018 10:56:24 GMT  
		Size: 193.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65a256578383b41646efb59a19af2c0dfb04ec56cd3461f208d08e00372e3eb1`  
		Last Modified: Sat, 22 Sep 2018 10:56:26 GMT  
		Size: 7.7 MB (7715005 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; ppc64le

```console
$ docker pull rabbitmq@sha256:471150e80601823c3b9a8fb47ec02831802ed61e95077ea08167f611d5ca8103
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.6 MB (71564161 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3ef86c8e2362adf535eb5879f5a5212f01dd7eb9e1a5029306d64d5876d18429`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Wed, 05 Sep 2018 08:19:50 GMT
ADD file:d599fe9ac09b7e23964896f5c79eb1a253ab4cfd9d27e3c409ff87a0cc012a33 in / 
# Wed, 05 Sep 2018 08:19:51 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 11:31:29 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 11:31:34 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 05 Sep 2018 11:31:35 GMT
ENV GOSU_VERSION=1.10
# Wed, 05 Sep 2018 11:32:03 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 05 Sep 2018 11:32:05 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 05 Sep 2018 11:34:45 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 11:34:48 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 05 Sep 2018 11:34:51 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 11:34:54 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Sat, 22 Sep 2018 08:29:28 GMT
ENV RABBITMQ_VERSION=3.7.8
# Sat, 22 Sep 2018 08:29:29 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Sat, 22 Sep 2018 08:29:30 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Sat, 22 Sep 2018 08:30:22 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Sat, 22 Sep 2018 08:30:25 GMT
ENV LANG=C.UTF-8
# Sat, 22 Sep 2018 08:30:26 GMT
ENV HOME=/var/lib/rabbitmq
# Sat, 22 Sep 2018 08:30:28 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Sat, 22 Sep 2018 08:30:39 GMT
VOLUME [/var/lib/rabbitmq]
# Sat, 22 Sep 2018 08:30:41 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Sat, 22 Sep 2018 08:30:43 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Sat, 22 Sep 2018 08:30:55 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Sat, 22 Sep 2018 08:30:58 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 22 Sep 2018 08:31:07 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 22 Sep 2018 08:31:08 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 22 Sep 2018 08:31:10 GMT
CMD ["rabbitmq-server"]
# Sat, 22 Sep 2018 08:31:31 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 22 Sep 2018 08:31:58 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Sat, 22 Sep 2018 08:32:00 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:92065d7cb20e14e29d25bb528f13bf94b0956f60664782bb1c43ce3192bf762b`  
		Last Modified: Wed, 05 Sep 2018 08:26:35 GMT  
		Size: 22.7 MB (22740533 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:579e7691721557327e3927ed84719e320cf6617c3acc48457fbe3ecd5d70f853`  
		Last Modified: Wed, 05 Sep 2018 11:41:34 GMT  
		Size: 4.4 MB (4360587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2457b86f9cd5532629687ff9153d277b80e5c5c805dfbba681b8a51bc205fcc5`  
		Last Modified: Wed, 05 Sep 2018 11:41:29 GMT  
		Size: 4.1 KB (4105 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e69a3893e8f4d42d93f333b4f7a04240b2f1f8efe56cbf832b105ae32483ce4`  
		Last Modified: Wed, 05 Sep 2018 11:41:30 GMT  
		Size: 920.5 KB (920546 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87de592d09499649ca13a67a2de44d7c46855451105c18148090363fc0cbb78c`  
		Last Modified: Wed, 05 Sep 2018 11:41:28 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54dd733fc519ab91b0b6f3b8dd93802dcff0937fa8db79069713e23b163526e8`  
		Last Modified: Wed, 05 Sep 2018 11:41:34 GMT  
		Size: 25.4 MB (25378924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70161d40899550476a55bade31bc5e0e735c4ca8803318ed7c1370946c7ebc01`  
		Last Modified: Sat, 22 Sep 2018 08:34:27 GMT  
		Size: 10.3 MB (10325845 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49ebe8c120af2d5327a3af173abe786ed49f8b73245005b32362fce5c6cba732`  
		Last Modified: Sat, 22 Sep 2018 08:34:23 GMT  
		Size: 2.3 KB (2264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82d0bc3e2a4b9cfee255c21e4b04280da963048c8448361528ee06a25584c35e`  
		Last Modified: Sat, 22 Sep 2018 08:34:23 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d898013a8c86393481ab0469058ec22bb6fe436e1c1a2630a4de118164c6b3d`  
		Last Modified: Sat, 22 Sep 2018 08:34:23 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc2e6de4feb935b3c11825f0894903590e2a6b059e53c3e73faf5f8804936600`  
		Last Modified: Sat, 22 Sep 2018 08:34:23 GMT  
		Size: 4.2 KB (4184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5760ba94169f92060fdfb0b4b2923580978c247695bb08c382dae2605ef71196`  
		Last Modified: Sat, 22 Sep 2018 08:34:24 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:389dd83932053d9aa869f7c2116672991d7567db9225cd0d946fa10c97ded528`  
		Last Modified: Sat, 22 Sep 2018 08:35:33 GMT  
		Size: 192.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:17eb5f47fc4afe027e048745ab3ce432aee1781fd2a838cee4449e9eff42c76b`  
		Last Modified: Sat, 22 Sep 2018 08:35:37 GMT  
		Size: 7.8 MB (7826228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; s390x

```console
$ docker pull rabbitmq@sha256:1d6f92ba76c5b258ab550dd3495d362ff6b57aeeb4908d7f3aa2b5df3d1892ac
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **70.8 MB (70825366 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:51bb4c094d73e9935cce5082f58afa88082030d88ee2687bac1338147c975fa8`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Wed, 05 Sep 2018 11:44:28 GMT
ADD file:f5f366bce70b148326259fed081f171c5f1789dbd1954137fb79deb38cf5cef1 in / 
# Wed, 05 Sep 2018 11:44:29 GMT
CMD ["bash"]
# Wed, 05 Sep 2018 14:10:00 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 14:10:01 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 05 Sep 2018 14:10:02 GMT
ENV GOSU_VERSION=1.10
# Wed, 05 Sep 2018 14:10:14 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 05 Sep 2018 14:10:15 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 05 Sep 2018 14:10:39 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 14:10:39 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 05 Sep 2018 14:10:39 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 05 Sep 2018 14:10:40 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Sat, 22 Sep 2018 11:52:41 GMT
ENV RABBITMQ_VERSION=3.7.8
# Sat, 22 Sep 2018 11:52:41 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.8
# Sat, 22 Sep 2018 11:52:41 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.8-1
# Sat, 22 Sep 2018 11:53:01 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Sat, 22 Sep 2018 11:53:01 GMT
ENV LANG=C.UTF-8
# Sat, 22 Sep 2018 11:53:01 GMT
ENV HOME=/var/lib/rabbitmq
# Sat, 22 Sep 2018 11:53:02 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Sat, 22 Sep 2018 11:53:02 GMT
VOLUME [/var/lib/rabbitmq]
# Sat, 22 Sep 2018 11:53:03 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Sat, 22 Sep 2018 11:53:03 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Sat, 22 Sep 2018 11:53:04 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Sat, 22 Sep 2018 11:53:04 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 22 Sep 2018 11:53:04 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 22 Sep 2018 11:53:05 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 22 Sep 2018 11:53:05 GMT
CMD ["rabbitmq-server"]
# Sat, 22 Sep 2018 11:53:18 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 22 Sep 2018 11:53:27 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Sat, 22 Sep 2018 11:53:27 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:599d69132c0524467aafceacede5f8ea0a07f3ae6d5c97a28cf25ce9e1cd4580`  
		Last Modified: Wed, 05 Sep 2018 11:49:20 GMT  
		Size: 22.3 MB (22334611 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:486c2c2490eb81017dce27f813906639a902cc88712d9ac2b0f82224a2be95c5`  
		Last Modified: Wed, 05 Sep 2018 14:14:13 GMT  
		Size: 4.5 MB (4529994 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c34d0bc6dcfc4dbdedfaa97c4ac5437d8e256e085c4e404c22abf6aa34f047ba`  
		Last Modified: Wed, 05 Sep 2018 14:14:10 GMT  
		Size: 4.1 KB (4077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f69d2beab3371bbcea2702a538b5f6eda37ed482f86855cf0ca02a0d2dd00372`  
		Last Modified: Wed, 05 Sep 2018 14:14:10 GMT  
		Size: 937.9 KB (937895 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e98d90ad4ad7cbbddb16ce5aadc5b254e7bd3e19aeb3fa70713ab6a7ca1be769`  
		Last Modified: Wed, 05 Sep 2018 14:14:11 GMT  
		Size: 358.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b383a5f1ccedcdefbf544f7e83e607fbb2a9a5dba102894b2e7586b6e8f832d`  
		Last Modified: Wed, 05 Sep 2018 14:14:13 GMT  
		Size: 25.1 MB (25078805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a18f4e0f49e5c7fa4c687917d2711b5dee2f80a3e06b4cd35385450cd49a3f7f`  
		Last Modified: Sat, 22 Sep 2018 11:54:34 GMT  
		Size: 10.3 MB (10336726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40f817c499e28671a761b29102f1075f4266d62c50f59d1a8192e68734114c41`  
		Last Modified: Sat, 22 Sep 2018 11:54:32 GMT  
		Size: 2.3 KB (2260 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7af28dd83da642844689cc7e923fa6a477334a538a94427783edf76e5a6e60c8`  
		Last Modified: Sat, 22 Sep 2018 11:54:32 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a16d662645f4c124673b53b668b196fa88672a13d41ea209944729b1c240d9cc`  
		Last Modified: Sat, 22 Sep 2018 11:54:32 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7eaf7df364b1c719e1dc362d2ced5c91f52c51c76cf4897e885348f825a44174`  
		Last Modified: Sat, 22 Sep 2018 11:54:32 GMT  
		Size: 4.2 KB (4182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c78726550584f511b41f178c9b0d98bf8fa0b90b3e89bb877ed2f6dabc559040`  
		Last Modified: Sat, 22 Sep 2018 11:54:32 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40d52d7a8d251becb3a4e66c2fcbbef5ba1fee87acc4406db9e4e4111abfe22b`  
		Last Modified: Sat, 22 Sep 2018 11:55:02 GMT  
		Size: 192.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b4b3a47e42bdef77cdb9bb967a922bc6768a0d9c3373d68a36d0a8084a69800`  
		Last Modified: Sat, 22 Sep 2018 11:55:04 GMT  
		Size: 7.6 MB (7595871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
