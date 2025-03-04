name: sauce
category: services
tags: guide
index: 0
title: WebdriverIO - Sauce Service
---

Sauce Service
=============

This service helps to integrate WebdriverIO and its WDIO testrunner with the [Sauce Labs](https://saucelabs.com/) service. It automatically sets the job status for you and updates all important job properties like job name, tags, availability or custom data. Having [Sauce Connect](https://wiki.saucelabs.com/display/DOCS/Sauce+Connect) integrated you only need some minor tweaks to your configuration to run all your tests through a secure tunnel.

## Installation

In order to use the service you need to download it from NPM:

```sh
$ npm install wdio-sauce-service --save-dev
```

## Configuration

In order to use the service you need to set user and key in your wdio.conf.js file. It will automatically uses Sauce Labs to run your integration tests. If you want to use Sauce Connect you just need to set sauceConnect: true.

```js
// wdio.conf.js
export.config = {
    // ...
    services: ['sauce'],
    user: process.env.SAUCE_USERNAME,
    key: process.env.SAUCE_ACCESS_KEY,
    sauceConnect: true,
    // ...
};
```

## Options

### user
Your Sauce Labs username.

Type: `String`

### key
Your Sauce Labs access key.

Type: `String`

### sauceConnect
If true it runs Sauce Connect and opens a secure connection between a Sauce Labs virtual machine running your browser tests.

Type: `Boolean`<br>
Default: `false`

### sauceConnectOpts
Apply Sauce Connect options (e.g. to change port number or logFile settings). See [this list](https://github.com/bermi/sauce-connect-launcher#advanced-usage) for more information.

Type: `Object`<br>
Default: `{}`
