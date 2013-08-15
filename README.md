pomelo-sync-redis-plugin
==================

sync plugin for pomelo(>=0.6)

pomelo-sync-redis-plugin is modified from [pomelo-sync-plugin](https://github.com/netease/pomelo-sync-plugin)

Use [pomelo-sync-redis](https://github.com/jiangzhuo/pomelo-sync-redis) to compose this plugin, you can check the detail information in [here](https://github.com/jiangzhuo/pomelo-sync-redis/blob/master/README.md).


#Installation

```
npm install pomelo-sync-plugin
```

#Usage

```
var sync = require('pomelo-sync-plugin');

//app.js

app.use(sync, {sync: {
  path: __dirname + '/app/dao/mapping', dbclient: mongoClient,
  port: 6379, //default is 6379
  host: "127.0.0.1" //default is 127.0.0.1,
  interval: 100000,
  isSyncer: true, // default is false
  keys:{
    MERGER_MAP_KEY: "POMELO:SYNC:MERGER:MAP", //key of mergerMap in redis
    USER_SET_KEY: "POMELO:SYNC:%s:SET", //key of user set, it is a key format
    FLUSH_SET_KEY: "POMELO:SYNC:FLUSH:SET" //key of flushQueue in redis
  }
}});

```
