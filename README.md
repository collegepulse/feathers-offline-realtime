# feathers-offline-realtime-immutable

[![Build Status](https://travis-ci.org/collegepulse/feathers-offline-realtime-immutable.svg?branch=master)](https://travis-ci.org/collegepulse/feathers-offline-realtime-immutable)
[![Coverage Status](https://coveralls.io/repos/github/collegepulse/feathers-offline-realtime-immutable/badge.svg?branch=master)](https://coveralls.io/github/collegepulse/feathers-offline-realtime-immutable?branch=master)

> Offline-first realtime replication with optimistic updates.

## Installation

```
npm install feathers-offline-realtime-immutable --save
```

## Usage

```javascript
const Realtime = require('feathers-offline-realtime-immutable');
const feathersClient = feathers()...;
const messages = feathersClient.service('/messages');

const messagesRealtime = new Realtime(messages, { subscriber: (records, last) => {
  /**
   * Store the records in your state manager. For example, if integrating with redux:
   *
   * store.dispatch(services.messages.store({ connected: messagesRealtime.connected, last, records }));
   *
   */
}});
```

## Documentation

You can read the docs [here](https://docs.feathersjs.com/guides/offline-first/readme.html).

## License

Copyright (c) 2017

Licensed under the [MIT license](LICENSE).
