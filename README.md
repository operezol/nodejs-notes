# node.js Notes
Basic node.js notes

## Index
- [Node.js installation in linux](https://github.com/operezol/nodejs-notes/blob/master/README.md#nodejs-installation-in-linux)
- [Run node in terminal in REPL mode \(Read Evaluate Print Loop\)](https://github.com/operezol/nodejs-notes/blob/master/README.md#run-node-in-terminal-in-repl-mode-read-evaluate-print-loop)
- [npm](https://github.com/operezol/nodejs-notes/blob/master/README.md#npm)  
  - [Install nodeunit with npm for to unit testing ](https://github.com/operezol/nodejs-notes/blob/master/README.md#install-nodeunit-with-npm-for-to-unit-testing)
    - [Create a test](https://github.com/operezol/nodejs-notes/blob/master/README.md#create-a-test)
    - [Use nodeunit to test entire test folder from node terminal](https://github.com/operezol/nodejs-notes/blob/master/README.md#use-nodeunit-to-test-entire-test-folder-from-node-terminal)

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

#### Create a test

Is recommended to first write test before start writing it's code

\/test\/Test\.js

```

  var objectNameToTest = require("../lib/objectFileName").objectName;
  
  exports["Test description"] = function(test){
  
    var whatEver = objectNameToTest.getWhatEver();
    
    var whatEverElse = 0;
    
    var booleanValue = whatEver > whatEverElse;
    
    test.equal(whatEver, whatEverElse);
    
    test.notEqual(whatEver, whatEverElse);
    
    test.ok(booleanValue);
    
  }
  
  
```

#### Use nodeunit to test entire test folder from node terminal

nodeunit test


