# netLog

> Logging network events.

进程: [主进程](../glossary.md#main-process)

```javascript
const {netLog} = require('electron')
console.log('Start recording net-logs')
netLog.startLogging('/path/to/net-log')
// After some network events
netLog.stopLogging(path => {
  console.log('Net-logs written to', path)
})
```

See [`--log-net-log`](chrome-command-line-switches.md#--log-net-logpath) to log network events throughout the app's lifecycle.

## 方法

### `netLog.startLogging(path)`

* `path` String - File path to record network logs.

Starts recording network events to `path`.

### `netLog.stopLogging([callback])`

* `callback` Function (選用) 
  * `path` String - File path to which network logs were recorded.

Stops recording network events. If not called, net logging will automatically end when app quits.

## 屬性

### `netLog.currentlyLogging`

A `Boolean` property that indicates whether network logs are recorded.

### `netLog.currentlyLoggingPath`

A `String` property that returns the path to the current log file.