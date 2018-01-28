# node.js Notes
Basic node.js notes

## Index
- [Node.js installation in linux](https://github.com/operezol/nodejs-notes/blob/master/README.md#nodejs-installation-in-linux)
- [Run node in terminal in REPL mode \(Read Evaluate Print Loop\)](https://github.com/operezol/nodejs-notes/blob/master/README.md#run-node-in-terminal-in-repl-mode-read-evaluate-print-loop)
- [Install nodeunit with npm for to unit testing ](https://github.com/operezol/nodejs-notes/blob/master/README.md#install-nodeunit-with-npm-for-to-unit-testing)

## Node.js installation in linux

sudo apt install curl && 
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash - && 
sudo apt-get install -y nodejs && 
sudo apt-get install -y build-essential

## Run node in terminal in REPL mode (Read Evaluate Print Loop)

node

2+2

### Break Terminal REPL input loop

.break

( or ctrl +c )

### Getting node help (basic commands)

.help

### Exit node terminal REPL

.exit

( or ctrl + c )

## npm

### Install nodeunit with npm for to unit testing 

npm i -g nodeunit


