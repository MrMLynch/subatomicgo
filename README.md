# subatomicgo
 Subatomic Go Web App - Test version

### Requirements
    - Go
    - Git
    - Komodo Daemon (jl777 branch compiled from http://github.com/jl777/komodo.git)


### Install Git, Komodo and Subatomic binaries
Follow this instruction guide and install `Komodo` and `subatomic` binaries on your system:
https://gist.github.com/himu007/add3181427bb53ab5dc5160537f0c238

### Install Go on your system
On Ubuntu can follow this guide: https://github.com/golang/go/wiki/Ubuntu

```shell
sudo add-apt-repository ppa:longsleep/golang-backports
sudo apt update
sudo apt install golang-go
```

On Mac can install Go using `brew`.

```shell
brew update
brew install go
```

### Installing SubatomicGo App
In Linux/Mac you must have a `go` directory under your `$HOME` directory in your OS.
If you don't find this directory then create the following:

```shell
mkdir -p $HOME/go/{bin,src,pkg}
```

```
go get -u github.com/satindergrewal/subatomicgo
cd $HOME/go/src/github.com/satindergrewal/subatomicgo
```

#### Configure config.json with absolute path of subatomic binary

You must configure the `config.json` file with full path where `subatomic` file is located.
For example if you have compiled and installed `Komodo` and `subatomic` as per the guide link provided earlier, you probably has the komodo compiled in your `$HOME/komodo` location.

Make a copy of `config.json` file from `config.json.sample` file:

```shell
cd $HOME/go/src/github.com/satindergrewal/subatomicgo
cp config.json.sample config.json
```

Open `config.json` in text editor and edit value of only `subatomic_dir` key.

To get the full path of your `komodo` directory `cd` to `komodo` directory and issue `pwd` command to get full path. Example:
```
cd $HOME/komodo/src
pwd
```

It will give full path for example like this:
```
/home/satinder/komodo/src
```

Replace the path you get from this output in `config.json` file.

Before:
```json
"subatomic_dir": "/Users/satinder/repositories/jl777/komodo/src"
```

After:
```json
"subatomic_dir": "/home/satinder/komodo/src"
```

#### Start SubatomicGo Web App

To start the app execute following command inside `subatomicgo` directory:
```shell
cd $HOME/go/src/github.com/satindergrewal/subatomicgo
go run main.go
```

Now open http://localhost:8080