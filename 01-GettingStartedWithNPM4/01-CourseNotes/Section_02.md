# npm Basics

## What is a Package?

* NPM used all open source front end development

## Module vs. Package

* Module: One javascript file
* Package: Multiple javascript file

## Typical npm Usage

* **Package.json** içerisinde bulunan datalara göre dependency ler install edilir.
* **Script** kısmında bulunan komutlar çalıştırılabilir.

```sh
onder@Onder-Dell-G15-5520:~/.../ToBeDeleted$ git clone git@github.com:joeeames/trip-to-mars-typical.git

onder@Onder-Dell-G15-5520:~/.../trip-to-mars-typical$ cat package.json
```

```JavaScript
{
  "name": "trip-to-mars",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "dependencies": {
    "express": "^4.17.1",
    "lodash": "^4.17.15"
  },
  "devDependencies": {
    "jshint": "^2.11.0"
  },
  "scripts": {
    "start": "node server.js",
    "test": "node test.js"
  },
  "author": "Joe Eames",
  "license": "ISC"
}
```

Install the package;

```sh
onder@Onder-Dell-G15-5520:~/.../trip-to-mars-typical$ npm install
# added 87 packages, and audited 88 packages in 9s
# 
# 10 packages are looking for funding
#   run `npm fund` for details
# 
# found 0 vulnerabilities
# npm notice 
# npm notice New minor version of npm available! 9.2.0 -> 9.6.4
# npm notice Changelog: https://github.com/npm/cli/releases/tag/v9.6.4
# npm notice Run npm install -g npm@9.6.4 to update!
# npm notice
```

```sh
onder@Onder-Dell-G15-5520:~/.../trip-to-mars-typical$ npm start
# > trip-to-mars@1.0.0 start
# > node server.js
# 
# App running on port 3000

onder@Onder-Dell-G15-5520:~/.../trip-to-mars-typical$ npm test
# > trip-to-mars@1.0.0 test
# > node test.js
# 
# 5 of 5 tests passed
```

## npm Help

```sh
onder@Onder-Dell-G15-5520:~/$ npm -h
onder@Onder-Dell-G15-5520:~/$ npm help install
```

# Creating a package.json

2 farklı proje türü var.
* User lar için web siteleri
* Third party ler için package oluşturulması

Dependency lerin takibini çok kolaylaştırır.

```sh
onder@Onder-Dell-G15-5520:~/.../01-Hello$ npm init
# This utility will walk you through creating a package.json file.
# It only covers the most common items, and tries to guess sensible defaults.
# 
# See `npm help init` for definitive documentation on these fields and exactly what they do.
# 
# Use `npm install <pkg>` afterwards to install a package and
# save it as a dependency in the package.json file.
# 
# Press ^C at any time to quit.

package name: (01-hello) onder-hello
version: (1.0.0) 0.1.0
description: Basic Hello World Application
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: Önder Görmez
license: (ISC) 

# About to write to /home/onder/Repos/JavaScript_Playground/02-Projects/01-Hello/package.json:
# 
# {
#   "name": "onder-hello",
#   "version": "0.1.0",
#   "description": "Basic Hello World Application",
#   "main": "index.js",
#   "scripts": {
#     "test": "echo \"Error: no test specified\" && exit 1"
#   },
#   "author": "Önder Görmez",
#   "license": "ISC"
# }

Is this OK? (yes) yes
onder@Onder-Dell-G15-5520:~/.../01-Hello$
```

## The package-lock.json File

Yüklediğimiz paketlerin dependency lerini gösterir.
* Source control e commitlenir.
* Developer ların hepsinde aynı alt paketlere bağımlı olmayı sağlar.

## Listing Installed Packages
"npm list" tüm bağımlı olunan paketleri gösterir.

"npm list --depth 1" bizim eklediğimiz ve onların direkt bağlı olduğu kütüphaneleri gösterir.

```sh
onder@Onder-Dell-G15-5520:~/.../01-Hello$ npm list --depth 1
# onder-hello@0.1.0 /home/onder/Repos/JavaScript_Playground/02-Projects/01-Hello
# └─┬ express@4.18.2
#   ├── accepts@1.3.8
#   ├── array-flatten@1.1.1
#   ├── body-parser@1.20.1
#   ├── content-disposition@0.5.4
#   ├── content-type@1.0.5
#   ├── cookie-signature@1.0.6
#   ├── cookie@0.5.0
#   ├── debug@2.6.9
#   ├── depd@2.0.0
#   ├── encodeurl@1.0.2
#   ├── escape-html@1.0.3
#   ├── etag@1.8.1
#   ├── finalhandler@1.2.0
#   ├── fresh@0.5.2
#   ├── http-errors@2.0.0
#   ├── merge-descriptors@1.0.1
#   ├── methods@1.1.2
#   ├── on-finished@2.4.1
#   ├── parseurl@1.3.3
#   ├── path-to-regexp@0.1.7
#   ├── proxy-addr@2.0.7
#   ├── qs@6.11.0
#   ├── range-parser@1.2.1
#   ├── safe-buffer@5.2.1
#   ├── send@0.18.0
#   ├── serve-static@1.15.0
#   ├── setprototypeof@1.2.0
#   ├── statuses@2.0.1
#   ├── type-is@1.6.18
#   ├── utils-merge@1.0.1
#   └── vary@1.1.2

onder@Onder-Dell-G15-5520:~/.../01-Hello$
```

Listeleme için -dev, -prod da mümkündür (npm list -prod)

## Installing Global Packages
npm install express --global

## Removing a Packages
npm uninstall express --global

## Installing Specific Versions
Semantic versioning 1.8.3  
1: Major version --> Can be break methods or class signature etc.  
8: Minor Version --> New feature or improvement  
3: Patch Version --> Bug or performance improvement

```sh
onder@Onder-Dell-G15-5520:~/.../01-Hello$ npm install underscore@1.8.2
# added 1 package, and audited 2 packages in 1s

onder@Onder-Dell-G15-5520:~/.../01-Hello$

# 1.8.2 versiyondan büyük ve 2.0.0 dan küçük bi tane yüklesin demek için;
onder@Onder-Dell-G15-5520:~/.../01-Hello$ npm install underscore@">1.8.2 <2.0.0"
# added 1 package, and audited 2 packages in 474ms

onder@Onder-Dell-G15-5520:~/.../01-Hello$ npm list --depth 0
# onder-hello@0.1.0 /home/onder/Repos/JavaScript_Playground/02-Projects/01-Hello
# └── underscore@1.13.6

onder@Onder-Dell-G15-5520:~/.../01-Hello$
```
