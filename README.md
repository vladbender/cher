# cher

This tool allows you to run programs written in different languages without the necessity of installing compilers or some other tooling.

## Usage

`cher` has 3 working modes:
- run
- repl
- shell

In **run** mode `cher` runs code in choosen language and prints output to the command line:
```bash
% ./cher run test_sources/main.rs
Hello from Rust! Do you know that 2^10 = 1024?
%
```

In **repl** mode `cher` runs REPL (read-eval-print-loop) in languages that have it:
```bash
% ./cher repl ruby 
irb(main):002:0> 2**42
=> 4398046511104
% 
```

In **shell** mode `cher` runs cli in docker container. In that cli you will have access to all tools in the choosen language. All files of the current directory are placed on `/workdir` path:
```bash
% ./cher shell go
/go$ cd /workdir/test_sources/
/workdir/test_sources$ go run main.go 
Hello from Golang!
/workdir/test_sources$ 
%
```

## Installation

On Linux or MacOS:
```bash
sudo curl https://raw.githubusercontent.com/vladislavvv/cher/main/cher --output /usr/local/bin/cher
sudo chmod +x /usr/local/bin/cher
```

## Tests

You can run tests with "Hello, world" programms:

**WARNING!** It will download a lot of docker images in every language.
```bash
./test
```

## Requirements

- docker

## Supported languages

- JavaScript (Node.js)
- TypeScript (Node.js)
- Golang
- Rust
- Python
- Ruby
- Java
- C/C++
- PHP
- Haskell

## TODO
- Other languages
- (?) сlean mode for deleting unnecessary images