# GoApp

An application for Go knowledge assessment.

## Description

This is a web application that utilises websockets. A client connects on `localhost:8080` and has three options: a) `open` a websocket connection that reads values from a counter b) `close` the websocket and c) reset the counter to zero. The counter is feeded from a random string generator. On WS session termination statistics for terminated session are printed.

The application has some problems described below that need to be addressed plus some new features that need implementation.

## Problems

### #1

The server prints statistics for each WS sessioned closed but it seems to only count one message while there are more send to each WS session, e.g.

```
2024/03/29 18:28:38 stats.go:11: session a938e316-8536-46e6-8633-bd309fbcf579 has received 1 messages
```

### #2

A more then normal memory usage is observed after many WS sessions which needs investigation.

### #3

A cross-site request forgery is reported by a security audit which needs fixing.

## New features

### A

Modify the random string generator to generate only hex values and verify its accuracy and resource usage.

### B

Extent the API to return the Hex value in WS connection.

### C

Create a command line client that opens a requested number of sessions simultaneously.
