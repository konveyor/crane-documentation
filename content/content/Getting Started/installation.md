---
title: "Installation"
date: 2021-11-16T12:36:42-05:00
draft: false
---

### Install latest released crane binary

```
curl -sL https://api.github.com/repos/konveyor/crane/releases/latest | 
jq -r ".assets[] | select(.name | contains(\"<arch>-<os>\")) | .browser_download_url" | wget -i-
chmod +x <binary>
cp <binary> /bin/usr/crane
```

Currently only three architectures are supported which are 

- amd64-linux
- amd64-darwin
- arm64-darwin

### Install most recent crane from upstream main branch

`GOPATH` should be configured to build the project.

```
cd $GOPATH
git clone https://github.com/konveyor/crane.git
cd crane
go build -o crane main.go
cp crane /bin/usr/crane
```

<b>Note:</b> It is recommended to install the released version instead of building from upstream main
