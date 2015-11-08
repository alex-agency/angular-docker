alexagency/angular-yeoman
==========================

**Dockerfile for [Yeoman](http://yeoman.io/) with [AngularJS](https://angularjs.org/) generator**

### Installation

Install [Docker Machine](https://docs.docker.com/machine/install-machine/).

Create virtual machine:
```
docker-machine create -d virtualbox dev
```

Get IP address:
```
docker-machine ip dev
```

Connect to virtual machine:
```
docker-machine ssh dev
```

Go to shared (between host and virtualbox) home directory:
```
cd /Users/<MAC USER>
cd /c/Users/<WINDOWS USER>
```

Run **alexagency/angular-yeoman** container from [Docker Hub](https://hub.docker.com/r/alexagency/angular-yeoman/):
```
docker run -it --rm -p 9000:9000 -v $(pwd)/angular:/app alexagency/angular-yeoman
```

Initiate one of Yeoman generators:

[AngularJS oficial generator](https://github.com/yeoman/generator-angular):
```
yo angular
```

Check generated project:
```
/Users/<MAC USER>/angular
/c/Users/<WINDOWS USER>/angular
```

Build:
```
grunt build --force
```

Run unit tests:
```
grunt test
```

Compile and launch:
```
sed -i s/localhost/0.0.0.0/g Gruntfile.js
grunt serve
```

Browse to Angular webapp:
```
http://<virtual machine ip>:9000/
```
