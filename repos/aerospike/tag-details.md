<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `aerospike`

-	[`aerospike:3.13.0.11`](#aerospike313011)
-	[`aerospike:4.1.0.6`](#aerospike4106)
-	[`aerospike:4.3.0.7`](#aerospike4307)
-	[`aerospike:latest`](#aerospikelatest)

## `aerospike:3.13.0.11`

```console
$ docker pull aerospike@sha256:eb8553e0195e836b886dec3ab7259b890c5c222d30ebd3f72e7e8db3db0b7272
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `aerospike:3.13.0.11` - linux; amd64

```console
$ docker pull aerospike@sha256:b9593f05f2c2eb04e9f3b4bdd3dd4867ce01531e22a99d9a4df7ef38043d8b9c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **70.2 MB (70237559 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2676223e6a9d52aee5357b2f9c18161df078c1016ac0959a52a611f26a17be4d`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["asd"]`

```dockerfile
# Wed, 05 Sep 2018 22:20:55 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 05 Sep 2018 22:20:55 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 05 Sep 2018 22:20:56 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 05 Sep 2018 22:20:57 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 05 Sep 2018 22:20:57 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 05 Sep 2018 22:20:57 GMT
CMD ["/bin/bash"]
# Wed, 05 Sep 2018 22:37:38 GMT
ENV AEROSPIKE_VERSION=3.13.0.11
# Wed, 05 Sep 2018 22:37:38 GMT
ENV AEROSPIKE_SHA256=6b3bb0da56185e66d5125cf5ec84706be153b51e90f36e31cc1c9e5620bc3ed4
# Wed, 05 Sep 2018 22:38:11 GMT
RUN apt-get update -y   && apt-get install -y wget python python-argparse python-bcrypt python-openssl logrotate net-tools iproute2 iputils-ping gettext-base  && wget "https://www.aerospike.com/artifacts/aerospike-server-community/${AEROSPIKE_VERSION}/aerospike-server-community-${AEROSPIKE_VERSION}-ubuntu16.04.tgz" -O aerospike-server.tgz   && echo "$AEROSPIKE_SHA256 *aerospike-server.tgz" | sha256sum -c -   && mkdir aerospike   && tar xzf aerospike-server.tgz --strip-components=1 -C aerospike   && dpkg -i aerospike/aerospike-server-*.deb   && dpkg -i aerospike/aerospike-tools-*.deb   && mkdir -p /var/log/aerospike/   && mkdir -p /var/run/aerospike/   && rm -rf aerospike-server.tgz aerospike /var/lib/apt/lists/*   && dpkg -r wget ca-certificates   && dpkg --purge wget ca-certificates   && apt-get purge -y
# Wed, 05 Sep 2018 22:38:12 GMT
COPY file:92f154ac5768cc66c29bd7ca3d00a0fe0ae8d08f1d309fdcda8bf66d4c73cadd in /etc/aerospike/aerospike.template.conf 
# Wed, 05 Sep 2018 22:38:12 GMT
COPY file:7eece3188902a85a78ecb96d2ec561fce45fa1728926bc66f3903d6955630907 in /entrypoint.sh 
# Wed, 05 Sep 2018 22:38:12 GMT
VOLUME [/opt/aerospike/data]
# Wed, 05 Sep 2018 22:38:12 GMT
EXPOSE 3000/tcp 3001/tcp 3002/tcp 3003/tcp
# Wed, 05 Sep 2018 22:38:12 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 05 Sep 2018 22:38:13 GMT
CMD ["asd"]
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:504facff238fde83f1ca8f9f54520b4219c5b8f80be9616ddc52d31448a044bd`  
		Last Modified: Wed, 05 Sep 2018 22:22:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebbcacd28e101968415b0c812b2d2dc60f969e36b0b08c073bf796e12b1bb449`  
		Last Modified: Wed, 05 Sep 2018 22:22:07 GMT  
		Size: 615.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7fb3351ecad291a88b92b600037e2435c84a347683d540042086fe72c902b8a`  
		Last Modified: Wed, 05 Sep 2018 22:22:06 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e3debadcbf7e542e2aefbce1b64a358b1931fb403b3e4aeca27cb4d809d56c2`  
		Last Modified: Wed, 05 Sep 2018 22:22:06 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d66b8830efbcaa8690260d8aa1f995fda03581bd45bb066dfb0dc2852413a765`  
		Last Modified: Wed, 05 Sep 2018 22:39:04 GMT  
		Size: 27.0 MB (26980576 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce273f19dffbac4a9295829d70de12304a5fdb45976fd5ed37b0681f5b743285`  
		Last Modified: Wed, 05 Sep 2018 22:38:59 GMT  
		Size: 1.1 KB (1113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49df69a5f0c6eb8c401b5e2a166fb9e8c67dd884ab483d62ee24dda1c6925e89`  
		Last Modified: Wed, 05 Sep 2018 22:38:59 GMT  
		Size: 884.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `aerospike:4.1.0.6`

```console
$ docker pull aerospike@sha256:b6b6bfb4517cd8aaf4a5a86116272cb3f8988ff0713de4448f443a82e5e99fda
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `aerospike:4.1.0.6` - linux; amd64

```console
$ docker pull aerospike@sha256:03d0d2a1d16788442cea51f3314bb400951b40c53b4b2cf91468ce194214f9f9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **44.6 MB (44585126 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ceac8900cb77b6fea5858268259a6bbdcc4cc5c0f9302befbe103db4104f0242`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["asd"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:34 GMT
ADD file:e6ca98733431f75e97eb09758ba64065d213d51bd2070a95cf15f2ff5adccfc4 in / 
# Tue, 04 Sep 2018 21:21:34 GMT
CMD ["bash"]
# Tue, 11 Sep 2018 21:19:21 GMT
ENV AEROSPIKE_VERSION=4.1.0.6
# Tue, 11 Sep 2018 21:19:21 GMT
ENV AEROSPIKE_SHA256=98e6d3a4e95bd8119b1d8b3b353a2b06ededd8ee9409401c2a6fc827881b4055
# Tue, 11 Sep 2018 21:19:41 GMT
RUN apt-get update -y   && apt-get install -y wget python lua5.2 gettext-base   && wget "https://www.aerospike.com/artifacts/aerospike-server-community/${AEROSPIKE_VERSION}/aerospike-server-community-${AEROSPIKE_VERSION}-debian9.tgz" -O aerospike-server.tgz   && echo "$AEROSPIKE_SHA256 *aerospike-server.tgz" | sha256sum -c -   && mkdir aerospike   && tar xzf aerospike-server.tgz --strip-components=1 -C aerospike   && dpkg -i aerospike/aerospike-server-*.deb   && dpkg -i aerospike/aerospike-tools-*.deb   && mkdir -p /var/log/aerospike/   && mkdir -p /var/run/aerospike/   && rm -rf aerospike-server.tgz aerospike /var/lib/apt/lists/*   && rm -rf /opt/aerospike/lib/java   && dpkg -r wget ca-certificates openssl xz-utils  && dpkg --purge wget ca-certificates openssl xz-utils  && apt-get purge -y   && apt autoremove -y
# Tue, 11 Sep 2018 21:19:42 GMT
COPY file:92f154ac5768cc66c29bd7ca3d00a0fe0ae8d08f1d309fdcda8bf66d4c73cadd in /etc/aerospike/aerospike.template.conf 
# Tue, 11 Sep 2018 21:19:42 GMT
COPY file:7eece3188902a85a78ecb96d2ec561fce45fa1728926bc66f3903d6955630907 in /entrypoint.sh 
# Tue, 11 Sep 2018 21:19:42 GMT
VOLUME [/opt/aerospike/data]
# Tue, 11 Sep 2018 21:19:42 GMT
EXPOSE 3000/tcp 3001/tcp 3002/tcp 3003/tcp
# Tue, 11 Sep 2018 21:19:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 11 Sep 2018 21:19:43 GMT
CMD ["asd"]
```

-	Layers:
	-	`sha256:802b00ed6f79f48e6a5f44ecbcaf43563d6077aaecb565eee1dfc615c0b18c00`  
		Last Modified: Tue, 04 Sep 2018 21:25:45 GMT  
		Size: 22.5 MB (22485965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b7e9ef117fbc77ea1538241eba61981ef419ead3208aaa4f2151f9d336815dc`  
		Last Modified: Tue, 11 Sep 2018 21:20:26 GMT  
		Size: 22.1 MB (22097170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b6de1818b496bf2cc80e9c8754d86c6a84511b23f8695690e3c04e582ba81b5`  
		Last Modified: Tue, 11 Sep 2018 21:20:21 GMT  
		Size: 1.1 KB (1108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a76c1ad3db27f2c14d4edc0227e7b22c385557c2a60c6062444272054f5d447b`  
		Last Modified: Tue, 11 Sep 2018 21:20:21 GMT  
		Size: 883.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `aerospike:4.3.0.7`

```console
$ docker pull aerospike@sha256:be20605233b212915afbe4c60dd4b468491268c1c69c0b58527b02676690991f
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `aerospike:4.3.0.7` - linux; amd64

```console
$ docker pull aerospike@sha256:83d24da149c8f1c5c1ae6315b2abe66a859cd5f9c078f0ffc78fb1a497a9f397
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **53.7 MB (53741683 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2882c984da766020e2950cdc2ce1ba954f49b1fc5ee081fcd5ec5cca1c36655a`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["asd"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:34 GMT
ADD file:e6ca98733431f75e97eb09758ba64065d213d51bd2070a95cf15f2ff5adccfc4 in / 
# Tue, 04 Sep 2018 21:21:34 GMT
CMD ["bash"]
# Tue, 11 Sep 2018 21:19:52 GMT
ENV AEROSPIKE_VERSION=4.3.0.7
# Tue, 11 Sep 2018 21:19:53 GMT
ENV AEROSPIKE_SHA256=7586e21fc9c53a152cdd58fb39e9d073ebc71d2898f6e134ae3b1b2deae44022
# Tue, 11 Sep 2018 21:20:08 GMT
RUN apt-get update -y   && apt-get install -y wget python lua5.2 gettext-base   && wget "https://www.aerospike.com/artifacts/aerospike-server-community/${AEROSPIKE_VERSION}/aerospike-server-community-${AEROSPIKE_VERSION}-debian9.tgz" -O aerospike-server.tgz   && echo "$AEROSPIKE_SHA256 *aerospike-server.tgz" | sha256sum -c -   && mkdir aerospike   && tar xzf aerospike-server.tgz --strip-components=1 -C aerospike   && dpkg -i aerospike/aerospike-server-*.deb   && dpkg -i aerospike/aerospike-tools-*.deb   && mkdir -p /var/log/aerospike/   && mkdir -p /var/run/aerospike/   && rm -rf aerospike-server.tgz aerospike /var/lib/apt/lists/*   && dpkg -r wget ca-certificates openssl xz-utils  && dpkg --purge wget ca-certificates openssl xz-utils  && apt-get purge -y   && apt autoremove -y
# Tue, 11 Sep 2018 21:20:08 GMT
COPY file:92f154ac5768cc66c29bd7ca3d00a0fe0ae8d08f1d309fdcda8bf66d4c73cadd in /etc/aerospike/aerospike.template.conf 
# Tue, 11 Sep 2018 21:20:08 GMT
COPY file:7eece3188902a85a78ecb96d2ec561fce45fa1728926bc66f3903d6955630907 in /entrypoint.sh 
# Tue, 11 Sep 2018 21:20:08 GMT
VOLUME [/opt/aerospike/data]
# Tue, 11 Sep 2018 21:20:08 GMT
EXPOSE 3000/tcp 3001/tcp 3002/tcp 3003/tcp
# Tue, 11 Sep 2018 21:20:09 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 11 Sep 2018 21:20:09 GMT
CMD ["asd"]
```

-	Layers:
	-	`sha256:802b00ed6f79f48e6a5f44ecbcaf43563d6077aaecb565eee1dfc615c0b18c00`  
		Last Modified: Tue, 04 Sep 2018 21:25:45 GMT  
		Size: 22.5 MB (22485965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1328cd8973277187b8026879c3e7b2ed5a397f914d598dc9b72969db7c88acd2`  
		Last Modified: Tue, 11 Sep 2018 21:20:40 GMT  
		Size: 31.3 MB (31253728 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30a7e8e2d016c3735b035f2b06c37eb037b10ec7044d2d0d02b291afb5cf4c15`  
		Last Modified: Tue, 11 Sep 2018 21:20:35 GMT  
		Size: 1.1 KB (1105 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d154b31f1b9619f377ab333252e2b58c318878cb207071613abb4c15c5e8a708`  
		Last Modified: Tue, 11 Sep 2018 21:20:35 GMT  
		Size: 885.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `aerospike:latest`

```console
$ docker pull aerospike@sha256:be20605233b212915afbe4c60dd4b468491268c1c69c0b58527b02676690991f
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `aerospike:latest` - linux; amd64

```console
$ docker pull aerospike@sha256:83d24da149c8f1c5c1ae6315b2abe66a859cd5f9c078f0ffc78fb1a497a9f397
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **53.7 MB (53741683 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2882c984da766020e2950cdc2ce1ba954f49b1fc5ee081fcd5ec5cca1c36655a`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["asd"]`

```dockerfile
# Tue, 04 Sep 2018 21:21:34 GMT
ADD file:e6ca98733431f75e97eb09758ba64065d213d51bd2070a95cf15f2ff5adccfc4 in / 
# Tue, 04 Sep 2018 21:21:34 GMT
CMD ["bash"]
# Tue, 11 Sep 2018 21:19:52 GMT
ENV AEROSPIKE_VERSION=4.3.0.7
# Tue, 11 Sep 2018 21:19:53 GMT
ENV AEROSPIKE_SHA256=7586e21fc9c53a152cdd58fb39e9d073ebc71d2898f6e134ae3b1b2deae44022
# Tue, 11 Sep 2018 21:20:08 GMT
RUN apt-get update -y   && apt-get install -y wget python lua5.2 gettext-base   && wget "https://www.aerospike.com/artifacts/aerospike-server-community/${AEROSPIKE_VERSION}/aerospike-server-community-${AEROSPIKE_VERSION}-debian9.tgz" -O aerospike-server.tgz   && echo "$AEROSPIKE_SHA256 *aerospike-server.tgz" | sha256sum -c -   && mkdir aerospike   && tar xzf aerospike-server.tgz --strip-components=1 -C aerospike   && dpkg -i aerospike/aerospike-server-*.deb   && dpkg -i aerospike/aerospike-tools-*.deb   && mkdir -p /var/log/aerospike/   && mkdir -p /var/run/aerospike/   && rm -rf aerospike-server.tgz aerospike /var/lib/apt/lists/*   && dpkg -r wget ca-certificates openssl xz-utils  && dpkg --purge wget ca-certificates openssl xz-utils  && apt-get purge -y   && apt autoremove -y
# Tue, 11 Sep 2018 21:20:08 GMT
COPY file:92f154ac5768cc66c29bd7ca3d00a0fe0ae8d08f1d309fdcda8bf66d4c73cadd in /etc/aerospike/aerospike.template.conf 
# Tue, 11 Sep 2018 21:20:08 GMT
COPY file:7eece3188902a85a78ecb96d2ec561fce45fa1728926bc66f3903d6955630907 in /entrypoint.sh 
# Tue, 11 Sep 2018 21:20:08 GMT
VOLUME [/opt/aerospike/data]
# Tue, 11 Sep 2018 21:20:08 GMT
EXPOSE 3000/tcp 3001/tcp 3002/tcp 3003/tcp
# Tue, 11 Sep 2018 21:20:09 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 11 Sep 2018 21:20:09 GMT
CMD ["asd"]
```

-	Layers:
	-	`sha256:802b00ed6f79f48e6a5f44ecbcaf43563d6077aaecb565eee1dfc615c0b18c00`  
		Last Modified: Tue, 04 Sep 2018 21:25:45 GMT  
		Size: 22.5 MB (22485965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1328cd8973277187b8026879c3e7b2ed5a397f914d598dc9b72969db7c88acd2`  
		Last Modified: Tue, 11 Sep 2018 21:20:40 GMT  
		Size: 31.3 MB (31253728 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30a7e8e2d016c3735b035f2b06c37eb037b10ec7044d2d0d02b291afb5cf4c15`  
		Last Modified: Tue, 11 Sep 2018 21:20:35 GMT  
		Size: 1.1 KB (1105 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d154b31f1b9619f377ab333252e2b58c318878cb207071613abb4c15c5e8a708`  
		Last Modified: Tue, 11 Sep 2018 21:20:35 GMT  
		Size: 885.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
