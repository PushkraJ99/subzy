## Subzy 

Subdomain takeover tool which works based on matching response fingerprints from [can-i-take-over-xyz](https://github.com/EdOverflow/can-i-take-over-xyz/blob/master/README.md) 

<a href="https://twitter.com/intent/follow?screen_name=return_0x">
        <img src="https://img.shields.io/twitter/follow/return_0x.svg?style=social&logo=twitter"
            alt="follow on Twitter"></a>


![Subzy subdomain takeover](https://i.imgur.com/ggB8zKx.png "Subzy subdomain takeover")

### Installation

```bash
go install -v github.com/PushkraJ99/subzy@latest
```

If `$GOBIN` and `$GOPATH` are [properly set](https://github.com/golang/go/wiki/SettingGOPATH#bash), execute the program as:

```bash
$ subzy --help
Subdomain takeover tool

Usage:
  subzy [command]

Available Commands:
  help        Help about any command
  run         Run subzy
  update      Update local fingerprints.json file
  version     Print subzy version

Flags:
  -h, --help   help for subzy

Use "subzy [command] --help" for more information about a command.
``` 

If you get an error `exec format error: ./subzy`, you need to [install Golang](https://golang.org/doc/install) for your OS and compile the program by running `go build -o subzy main.go` which will generate new `subzy` binary file

One Liner to Install Golang

```bash
wget https://gist.githubusercontent.com/PushkraJ99/5e8f27ebba4ad1ca75691fd23ade1ff2/raw/1e33a5422e32c8d020fc04f0570ecac99a343adc/golang.sh ;chmod 777 golang.sh ;sudo ./golang.sh
```


### Options

Only required flag for `run` subcommand(`r` short version) is either `--target` or `--targets`  

`--target` (string) - Set single or multiple (comma separated) target subdomain/s  
`--targets` (string) - File name/path to list of subdomains    
`--concurrency` (integer) - Number of concurrent checks (default 10)    
`--hide_fails` (boolean) - Hide failed checks and invulnerable subdomains (default false)    
`--https` (boolean) - Use HTTPS by default if protocol not defined on targeted subdomain (default false)  
`--timeout` (integer) - HTTP request timeout in seconds (default 10)  
`--verify_ssl` (boolean) - If set to true, it won't check site with invalid SSL

### Usage

Target subdomain can have protocol defined, if not `http://` will be used by default if `--https` not specifically set to true.

-  List of subdomains
   - ````./subzy run --targets list.txt````

- Single or multiple targets 
  - ```./subzy run --target test.google.com```
  - ```./subzy run --target test.google.com,https://test.yahoo.com```

### Command aliases

Each `subzy` subcommand has its own short version. Running `subzy version` or `subzy v` is the same.

* run - r
* update - u
* version - v
