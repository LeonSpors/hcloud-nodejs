# hcloud-nodejs

[![NPM Version][npm-image]][npm-url]
[![NPM Downloads][downloads-image]][downloads-url]

hcloud is a node.js package for [Hetzner cloud](https://www.hetzner.de/cloud) that can be used to manage your projects.

* [Installation](#installation)
* [Usage](#usage)
  * [Getting started](#getting-started)
  * [Examples](#examples)
  * [Full list of functions](#full-list-of-functions)
* [License](#license)
* [Author](#author)

## Installation

This is a [Node.js](https://nodejs.org/en/) module available through the
[npm registry](https://www.npmjs.com/). Installation is done using the
[`npm install` command](https://docs.npmjs.com/getting-started/installing-npm-packages-locally):

```sh
$ npm install hcloud-nodejs
```

## Usage

### Getting started

You have to register your client(api token) first. To obtain an api token go to your project on [Hetzner Cloud Console](https://console.hetzner.cloud/projects) and navigate to access.
```javascript
var hcloud = require('./index')
hcloud.registerClient('7JciVOnx2hKiPXv2AeZmSGAWczWrDFjGohxAYEfnLWfFF5vDwUbT4hRB3BE3lF3E')
```

### Examples
```javascript
hcloud.server().create({
        name                : 'server01',
        server_type         : 'cx11',
        location            : 'nbg1',
        start_after_create  : false,
        image               : 'ubuntu-16.04',
    }, (callback) => {
        console.log(callback)
    })
```

```javascript
hcloud.server().getAll((callback) => {
        console.log(callback)
    })
```

```javascript
hcloud.server(920754).poweron((callback) => {
        console.log(callback)
    })
```


### Full list of functions
* datacenter(id).get()
* datacenter(id).getAll()
* location(id).get()
* location(id).getAll()
* server().create(body, callback)
* server().getAll(callback)
* server(id).get(callback)
* server(id).changeName(name, callback)
* server(id).delete(callback)
* server(id).poweron(callback)
* server(id).shutdown(callback)
* server(id).reboot(callback)
* server(id).reset(callback)
* server(id).resetRootPassword(callback)
* server(id).enableRescue(callback)
* server(id).disableRescue(callback)
* server(id).requestConsole(callback)

## Documentation

[Offical API Documentation](https://docs.hetzner.cloud/)

## License

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.en.html)

## Author

[Leon Spors](https://github.com/halfbax) ([business@spors.io](mailto:business@spors.io))

[downloads-image]: https://img.shields.io/npm/dm/hcloud-nodejs.svg
[downloads-url]: https://npmjs.org/package/hcloud-nodejs
[npm-image]: https://img.shields.io/npm/v/hcloud-nodejs.svg
[npm-url]: https://npmjs.org/package/hcloud-nodejs
