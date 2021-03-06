## `registry:latest`

```console
$ docker pull registry@sha256:5a156ff125e5a12ac7fdec2b90b7e2ae5120fa249cf62248337b6d04abc574c8
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `registry:latest` - linux; amd64

```console
$ docker pull registry@sha256:a25e4660ed5226bdb59a5e555083e08ded157b1218282840e55d25add0223390
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **10.7 MB (10688384 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2e2f252f3c88679f1207d87d57c07af6819a1a17e22573bcef32804122d2f305`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["\/etc\/docker\/registry\/config.yml"]`

```dockerfile
# Tue, 11 Sep 2018 22:20:45 GMT
ADD file:4b806a0c031f19a4609ebde02464b2139efebfdf9f5d1bba13cf1c316938530d in / 
# Tue, 11 Sep 2018 22:20:45 GMT
CMD ["/bin/sh"]
# Wed, 12 Sep 2018 03:24:50 GMT
RUN set -ex     && apk add --no-cache ca-certificates apache2-utils
# Wed, 12 Sep 2018 03:24:51 GMT
COPY file:b99d4fe47ad1addf0e8f244236e05177f3bfe9eb3ddd59f08b67b2612d77c621 in /bin/registry 
# Wed, 12 Sep 2018 03:24:51 GMT
COPY file:6c4758d509045dc45381fa2df2e7ffcc661afcaa29805c75f8f1976f2b016db8 in /etc/docker/registry/config.yml 
# Wed, 12 Sep 2018 03:24:51 GMT
VOLUME [/var/lib/registry]
# Wed, 12 Sep 2018 03:24:51 GMT
EXPOSE 5000/tcp
# Wed, 12 Sep 2018 03:24:51 GMT
COPY file:7b57f7ab1a8cf85c00768560fffc926543a60c9c9f7a2b172767dcc9a3203394 in /entrypoint.sh 
# Wed, 12 Sep 2018 03:24:52 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 12 Sep 2018 03:24:52 GMT
CMD ["/etc/docker/registry/config.yml"]
```

-	Layers:
	-	`sha256:d6a5679aa3cfc52503fac8e2345790783537564df5af43355ec662d7703aacbf`  
		Last Modified: Tue, 11 Sep 2018 22:22:09 GMT  
		Size: 2.4 MB (2387846 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad0eac849f8f2014e20df11d611e4453c94a365a71eb3a90f02d8500391e1787`  
		Last Modified: Wed, 12 Sep 2018 03:25:16 GMT  
		Size: 2.0 MB (2034577 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2261ba058a15e3f21a467b1b02ea206d40cf0632d6b1aeee2ad200b662ed4aff`  
		Last Modified: Wed, 12 Sep 2018 03:25:17 GMT  
		Size: 6.3 MB (6265380 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f296fda86f10cfcb81d60d5bcb47a7784a8ec4876d6eac7fabd51f2a7e8694aa`  
		Last Modified: Wed, 12 Sep 2018 03:25:15 GMT  
		Size: 369.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcd4a541795bb9981999ce8f6e2e1c92e55b0041256153d2458ff35fb9381063`  
		Last Modified: Wed, 12 Sep 2018 03:25:15 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
