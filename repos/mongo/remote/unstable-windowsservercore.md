## `mongo:unstable-windowsservercore`

```console
$ docker pull mongo@sha256:be69d393500c2fb9138b0ee99f5857fbf0e35ae87389a653e678b4777d70f001
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2485; amd64
	-	windows version 10.0.16299.665; amd64
	-	windows version 10.0.17134.285; amd64

### `mongo:unstable-windowsservercore` - windows version 10.0.14393.2485; amd64

```console
$ docker pull mongo@sha256:fcbfafc989691c57a50bdbec130fab280f303614e2e143dae7de36126c7782b3
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.7 GB (5658464278 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e2fe3ef3b5d68962e9e80c2ecd8e750ea533059650a13bd592132894e152ed7d`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Tue, 11 Sep 2018 16:53:50 GMT
RUN Install update 10.0.14393.2485
# Sat, 15 Sep 2018 09:16:40 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Sat, 15 Sep 2018 09:42:40 GMT
ENV MONGO_VERSION=4.1.3
# Sat, 15 Sep 2018 09:42:40 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.3-signed.msi
# Sat, 15 Sep 2018 09:42:41 GMT
ENV MONGO_DOWNLOAD_SHA256=58d1aced38f597dbbff4930a82f7b7fbe9affc00e837ae688790a3f3ed52250e
# Fri, 21 Sep 2018 10:12:27 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 21 Sep 2018 10:12:28 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 21 Sep 2018 10:12:30 GMT
EXPOSE 27017/tcp
# Fri, 21 Sep 2018 10:12:31 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 18 Sep 2018 20:20:50 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:6e046b8e194c642cfc4d7dcaa12ec2f9359e1f54dbc7088ee9ca188416d5c553`  
		Last Modified: Tue, 11 Sep 2018 16:53:50 GMT  
		Size: 1.5 GB (1515870209 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:f786254e0429ce7f1ddc69d592364c6179e4c72da867230a987eba95e7d61708`  
		Last Modified: Fri, 21 Sep 2018 10:20:04 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c10aa54b7c6669c432ace49d98196d00032b4b1cbdc974368cad57ef75047837`  
		Last Modified: Fri, 21 Sep 2018 10:24:42 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae4c3ff5b982f152d75c5c790f51bf03bbf94cb440e6d68fb3e77cfe2c531b32`  
		Last Modified: Fri, 21 Sep 2018 10:24:42 GMT  
		Size: 1.2 KB (1205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33f7d621cf88cf58cb098dffab7125d9f4658477bafc2bd21459de965a0f0a0f`  
		Last Modified: Fri, 21 Sep 2018 10:24:40 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a88b803189cea0aa66ea15779de326b029986c2515927329e17b49195c9e1570`  
		Last Modified: Fri, 21 Sep 2018 10:24:56 GMT  
		Size: 72.6 MB (72599795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72c7b248aa662f6471be8d73467fd3f5455bcbbf89075ef114b8f9521502e664`  
		Last Modified: Fri, 21 Sep 2018 10:24:40 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8a6250daa956ac0cbb2537977cdfd2c51b86e127cac428282bb97c8e0c9de52`  
		Last Modified: Fri, 21 Sep 2018 10:24:40 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824d528f5c1750f455948e5c224d36b022da848d99c716e3c119d5962d877ebb`  
		Last Modified: Fri, 21 Sep 2018 10:24:40 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable-windowsservercore` - windows version 10.0.16299.665; amd64

```console
$ docker pull mongo@sha256:95d7b31d7ec981076ba8f888ee13be0f89210ebfbb9746a2c64a49c568b5fc9f
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.2 GB (3200210565 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:93b4086da3918dce4622ebb125798c0d48ab9734f6d568e3e3331862f60bb4db`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Sun, 09 Sep 2018 17:24:12 GMT
RUN Install update 10.0.16299.665
# Sat, 15 Sep 2018 09:20:18 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Sat, 15 Sep 2018 09:45:49 GMT
ENV MONGO_VERSION=4.1.3
# Sat, 15 Sep 2018 09:45:50 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.3-signed.msi
# Sat, 15 Sep 2018 09:45:51 GMT
ENV MONGO_DOWNLOAD_SHA256=58d1aced38f597dbbff4930a82f7b7fbe9affc00e837ae688790a3f3ed52250e
# Fri, 21 Sep 2018 10:15:56 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 21 Sep 2018 10:15:58 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 21 Sep 2018 10:16:00 GMT
EXPOSE 27017/tcp
# Fri, 21 Sep 2018 10:16:01 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 18 Sep 2018 22:35:04 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:a5b83e25f92aef992a2827d664111b4726ada7d0b13d7af21882734cab96d8d0`  
		Last Modified: Tue, 11 Sep 2018 17:07:56 GMT  
		Size: 858.3 MB (858335510 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:e4cdc6ca9b93c706388b66a6275c76b641997dbef9a73356ba7a8511a95ccd52`  
		Last Modified: Fri, 21 Sep 2018 10:20:28 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8d7dd8889b5fbefe2c2a96782e6fcc52611e8419476b1bf2efc342fc90868ae`  
		Last Modified: Fri, 21 Sep 2018 10:25:12 GMT  
		Size: 1.2 KB (1216 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05633ec54e7ddf372ebef733e95dbb05e0a87d3b1fb3b9caf0463544d18a6ea5`  
		Last Modified: Fri, 21 Sep 2018 10:25:12 GMT  
		Size: 1.2 KB (1208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f6b94981f1df8ff786bc00f97ead02198d32c2c61beba22b8f978824ff28476`  
		Last Modified: Fri, 21 Sep 2018 10:25:10 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b31501610583d27e9aee6a833e042263652c135393b97ad3159efec25ec0eccd`  
		Last Modified: Fri, 21 Sep 2018 10:25:27 GMT  
		Size: 67.6 MB (67566081 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccf093b6ec2c2061d6562f47072e61beb2d65973fa2e8004741c91aec3c4dd7e`  
		Last Modified: Fri, 21 Sep 2018 10:25:10 GMT  
		Size: 1.2 KB (1186 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba98366574b6a2c0bcb28923364ed1e4e1f35d102b8604a5bc676bb6596e6ddb`  
		Last Modified: Fri, 21 Sep 2018 10:25:10 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e027935e39fab67eae0b9a4c72896635a241f7b5a67a64d60e27557464f26a0`  
		Last Modified: Fri, 21 Sep 2018 10:25:10 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable-windowsservercore` - windows version 10.0.17134.285; amd64

```console
$ docker pull mongo@sha256:d1a2c37a4d6c3b3416c391fddeacd937d0b634f966f7b156f0ede4b314a03b06
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **2.3 GB (2274351325 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a807cbdd35830dc92cc493c9f87eb07b889153c8d4bc39ebe92f3fa706db70b`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Thu, 12 Apr 2018 09:20:54 GMT
RUN Apply image 10.0.17134.1
# Sun, 09 Sep 2018 17:20:44 GMT
RUN Install update 10.0.17134.285
# Sat, 15 Sep 2018 09:39:57 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Sat, 15 Sep 2018 09:48:19 GMT
ENV MONGO_VERSION=4.1.3
# Sat, 15 Sep 2018 09:48:20 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.3-signed.msi
# Sat, 15 Sep 2018 09:48:21 GMT
ENV MONGO_DOWNLOAD_SHA256=58d1aced38f597dbbff4930a82f7b7fbe9affc00e837ae688790a3f3ed52250e
# Fri, 21 Sep 2018 10:19:05 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 21 Sep 2018 10:19:07 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 21 Sep 2018 10:19:09 GMT
EXPOSE 27017/tcp
# Fri, 21 Sep 2018 10:19:10 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:d9e8b01179bfc94a5bdb1810fbd76b999aa52016001ace2d3a4c4bc7065a9601`  
		Last Modified: Tue, 18 Sep 2018 22:43:55 GMT  
		Size: 1.7 GB (1659688273 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:9f036448990c273bb1accf8d436799639bbb644326ae47f30fe4faed21c8d8d9`  
		Last Modified: Tue, 11 Sep 2018 17:11:59 GMT  
		Size: 547.2 MB (547225773 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:72421b921bc76cd58967f35b89a741539cec39dab3ff330e790096ac6853216a`  
		Last Modified: Fri, 21 Sep 2018 10:24:09 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01874927ef78b40cc4812d0143cbe1a9aa289e8b836d7f80caec477e0eb88dc4`  
		Last Modified: Fri, 21 Sep 2018 10:25:47 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79be5af18f21c11fbee2bbdaa234d2a455fe62a5e99c4117e720245abb13492f`  
		Last Modified: Fri, 21 Sep 2018 10:25:46 GMT  
		Size: 1.2 KB (1205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6117c24450ad288f5f838e4553e923e365862af30f823d6292d9f79a6dac1472`  
		Last Modified: Fri, 21 Sep 2018 10:25:43 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6ad6e20a9b78536e1767197a4ed7cbe0bbc21b5ae7bb84979476cdc3c30e408`  
		Last Modified: Fri, 21 Sep 2018 10:26:00 GMT  
		Size: 67.4 MB (67428885 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e4b7ca7cb1b88221d39fc758d723ac11176c8fc869e2e5b8dbbc9d9ae930e00`  
		Last Modified: Fri, 21 Sep 2018 10:25:43 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64c7ab056c95598a7d83cf5339abf2dc992a42926d4b0c608cabca193196a891`  
		Last Modified: Fri, 21 Sep 2018 10:25:44 GMT  
		Size: 1.2 KB (1203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cf1d965e2250ae3e61c70c14f08735696b228467b5e413611bcc54ec9aa2219`  
		Last Modified: Fri, 21 Sep 2018 10:25:43 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
