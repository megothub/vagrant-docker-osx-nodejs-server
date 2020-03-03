# Simple Vagrant plus Node.js in a Docker container example

Inspired by [Seanmatthews/vagrant-docker-osx-nodejs-server](https://github.com/Seanmatthews/vagrant-docker-osx-nodejs-server)


## Usage

Make sure you have [Vagrant](https://www.vagrantup.com/downloads.html) and [Docker (Stable)](https://hub.docker.com/editions/community/docker-ce-desktop-mac) installed. Then, clone that repo and start everything with:
```bash
vagrant up
```

You can check that your server is running with:
```bash
curl http://localhost:3000
```

Or simply point your browser to:
```
localhost:3000
```

Use the following command to connect to the container:
```
vagrant docker-exec -it -- /bin/bash
```

### Tested with the following software
* macOS Catalina: 10.15.3
* Vagrant: 2.2.7
* Docker Desktop: 2.2.0.3 (42716)
* Docker Engine: 19.03.5
* Node.js: 12.16.1

### Vagrantfile
This is the main Vagrantfile, which runs the Docker container

### Dockerfile
This is where the Docker magic happens. There's not much going on here--
Ubuntu updates its repos, installs Node.js, creates a public www directory,
moves out Node.js app to it, then runs it.

### app.js
This is the super simple Node.js server. It responds to everything with
'Hello World'. No ip is specified, so it defaults to '0.0.0.0' within the container.
