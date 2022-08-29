# wait.sh

Wait for services to start before running a command.

## Usage

### Docker

```Dockerfile
# syntax=docker/dockerfile:1.3
FROM alpine:latest
COPY --from=harrybrwn/wait.sh:latest /wait.sh /usr/local/bin
```

### Command Line

```
Wait for a remote endpoint to be accessable before
continuing or running a command.

Usage
  wait.sh <locations...> [flags...] [--] <command>

Flags
     --help     print help message
  -w --wait     seconds to wait between failures (default: 1)
  -t --timeout  timeout in seconds (default: 15)

Examples
  $ wait.sh http://localhost:8080 -- ls
  $ wait.sh tcp://example.com:80
  $ wait.sh -t 2 localhost:4444 -- echo yes
  $ wait.sh udp://localhost:5432 --wait 10 -- echo up...
```

