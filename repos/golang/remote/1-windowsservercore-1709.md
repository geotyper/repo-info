## `golang:1-windowsservercore-1709`

```console
$ docker pull golang@sha256:352fa1c1cc380e291f28e3876a5d68ba5f1c0b6f9ce04fe3b4cbf9f13af8e684
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.611; amd64

### `golang:1-windowsservercore-1709` - windows version 10.0.16299.611; amd64

```console
$ docker pull golang@sha256:670d871bf44ea20650b103aeb7de1cd31c1362805448b5407b3f44d7d875cae9
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.3 GB (3281367467 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:01a7659725712d182a581bf175c8e2ead5e04b852e5ba9231686005e1eb0ca8a`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 08 Aug 2018 23:20:54 GMT
RUN Install update 10.0.16299.611
# Wed, 15 Aug 2018 09:39:55 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Thu, 23 Aug 2018 10:41:07 GMT
ENV GIT_VERSION=2.11.1
# Thu, 23 Aug 2018 10:41:08 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Thu, 23 Aug 2018 10:41:09 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Thu, 23 Aug 2018 10:41:10 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Thu, 23 Aug 2018 10:42:36 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Thu, 23 Aug 2018 10:42:38 GMT
ENV GOPATH=C:\gopath
# Thu, 23 Aug 2018 10:43:34 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Mon, 27 Aug 2018 22:31:33 GMT
ENV GOLANG_VERSION=1.11
# Mon, 27 Aug 2018 22:37:49 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = '29f9291270f0b303d0b270f993972ead215b1bad3cc674a0b8a09699d978aeb4'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Mon, 27 Aug 2018 22:37:50 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 18 Sep 2018 22:35:04 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c4047f78756c2319eb99557ec7139906cf11af6c91aefcc0e44ac49a5481d8e4`  
		Last Modified: Mon, 13 Aug 2018 18:28:41 GMT  
		Size: 837.8 MB (837835144 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:ddd10e03dfdc774fc9b5f720df0030a8f59a8c2c78e843c72b45c30af480dc60`  
		Last Modified: Wed, 15 Aug 2018 09:54:44 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c12058357a053c6542d38c7a21e113d4ce7a615e5eb4f8807c4230d1b4031ea`  
		Last Modified: Thu, 23 Aug 2018 11:57:33 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd90e596423afd7a8f1e01b0a8d2d231f19b6e640f1c5e4b5de7c49e597ad7d7`  
		Last Modified: Thu, 23 Aug 2018 11:57:32 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54632cb246968a723c80e586ff81c81da034144191691b10cbaa26ceb8dbf4a0`  
		Last Modified: Thu, 23 Aug 2018 11:57:30 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5bf35363b2dd3eb1a4bb0e62d2db26a4a2defa6ca083a9dee30f73056e80d028`  
		Last Modified: Thu, 23 Aug 2018 11:57:29 GMT  
		Size: 1.2 KB (1203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf3cff204ef4c60216860767897bfa56b59ae3014ac7e76295086bba5e8cefd2`  
		Last Modified: Thu, 23 Aug 2018 11:57:42 GMT  
		Size: 29.2 MB (29161634 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa232763dbc5580f4156b40c2519f368a45b93a7d91097d45474e894e1dbae2d`  
		Last Modified: Thu, 23 Aug 2018 11:57:25 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f6d57d06ca4925eb2814abf9499002d83469fa132f97689c46663f159390605`  
		Last Modified: Thu, 23 Aug 2018 11:57:28 GMT  
		Size: 4.7 MB (4726635 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:224b47180770397003a91dcb53a06c4bcc73dbb02303d4cc78a49203693452e6`  
		Last Modified: Mon, 27 Aug 2018 23:15:47 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b76cdd4b407a878dcf3f4f22bca9ca3dc7b2a3ffdd5dd76acfdf768a161dc8e6`  
		Last Modified: Mon, 27 Aug 2018 23:17:23 GMT  
		Size: 135.3 MB (135333758 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55aabc3a120fb241d8813a57506a15a5b1bdf52b05c471c57813ea43229aea77`  
		Last Modified: Mon, 27 Aug 2018 23:15:47 GMT  
		Size: 1.3 KB (1349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
