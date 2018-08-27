## How to build from sources
- [Install Golang 1.9 or newer](https://golang.org/dl/)
```bash
go get -d -u github.com/cloudradar-monitoring/cagent
go build -o -ldflags="-X main.VERSION=$(git --git-dir=src/github.com/cloudradar-monitoring/cagent/.git describe --always --long --dirty --tag)" cagent github.com/cloudradar-monitoring/cagent/cmd/cagent
```

## How to run
***-r** for _one run only_ mode*
```bash
./cagent -r -o result.out
```

## Configuration
Check the [example config](https://github.com/cloudradar-monitoring/cagent/blob/master/example.config.toml)

Default locations:
* Mac OS: `~/.cagent/cagent.conf`
* Windows: `./cagent.conf`
* UNIX: `/etc/cagent/cagent.conf`

## Logs location
* Mac OS: `~/.cagent/cagent.log`
* Windows: `./cagent.log`
* UNIX: `/etc/cagent/cagent.conf`

## Build binaries and deb/rpm packages
– Install [goreleaser](https://goreleaser.com/introduction/)
```bash
CAGENT_VERSION=$(git describe --always --long --dirty --tag) goreleaser --snapshot
```

## Build MSI package
– Should be done on Windows machine
– Open command prompt(cmd.exe)
– Go to cagent directory `cd path_to_directory`
– Run `goreleaser --snapshot` to build binaries
– Run `build-win.bat`