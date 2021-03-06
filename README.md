# node.js Notes
Basic node.js notes

## Index
- [Node.js installation in linux](https://github.com/operezol/nodejs-notes/blob/master/README.md#nodejs-installation-in-linux)
- [Run node in terminal in REPL mode \(Read Evaluate Print Loop\)](https://github.com/operezol/nodejs-notes/blob/master/README.md#run-node-in-terminal-in-repl-mode-read-evaluate-print-loop)
- [npm (node package manager)](https://github.com/operezol/nodejs-notes/blob/master/README.md#npm-node-package-manager)  
  - [Install missing packages (dependencies) from cloned repository](https://github.com/operezol/nodejs-notes/blob/master/README.md#install-missing-packages-dependencies-from-cloned-repository)
  - [Initialize a new node repository](https://github.com/operezol/nodejs-notes/blob/master/README.md#initialize-a-new-node-repository)
    - [get, set, delete configurations to package.json with npm](https://github.com/operezol/nodejs-notes/blob/master/README.md#get-set-delete-configurations-to-packagejson-with-npm)
    - [Add packages to package.json with npm](https://github.com/operezol/nodejs-notes/blob/master/README.md#add-packages-to-packagejson-with-npm)
    - [Add package for development environment](https://github.com/operezol/nodejs-notes/blob/master/README.md#add-package-for-development-environment)
    - [Add package globaly (for all projects)](https://github.com/operezol/nodejs-notes/blob/master/README.md#add-package-globaly-for-all-projects)
  - [Install nodeunit with npm for to unit testing ](https://github.com/operezol/nodejs-notes/blob/master/README.md#install-nodeunit-with-npm-for-to-unit-testing)
    - [Create a test](https://github.com/operezol/nodejs-notes/blob/master/README.md#create-a-test)
    - [Reset Object Tested after each test](https://github.com/operezol/nodejs-notes/blob/master/README.md#reset-object-tested-after-each-test)
    - [Use nodeunit to test entire test folder from node terminal](https://github.com/operezol/nodejs-notes/blob/master/README.md#use-nodeunit-to-test-entire-test-folder-from-node-terminal)
  - [Install express.js to build a web server with npm](https://github.com/operezol/nodejs-notes/blob/master/README.md#install-expressjs-to-build-a-web-server-with-npm)
    - [Build web server with express](https://github.com/operezol/nodejs-notes/blob/master/README.md#build-web-server-with-express)
      - [Routing with express](https://github.com/operezol/nodejs-notes/blob/master/README.md#routing-with-express)
      - [Getting parameters from URL with express](https://github.com/operezol/nodejs-notes/blob/master/README.md#getting-parameters-from-url-with-express)


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

## npm (node package manager)

### Install missing packages (dependencies) from cloned repository

For weight purposes, node repositories do not contain the necessary packages (dependencies). That's why they should be installed / downloaded for the first time with this command.

```
npm install
```

### Initialize a new node repository

When a new node repository / project is started, libraries / packages / dependencies are needed and, to declare them, a package.json file is required. NPM can create this file with this command:

```
npm init
```

#### get, set, delete configurations to package.json with npm

All configurations within the package.json file can be edited, consulted, or deleted through npm for their pair of setters and getters.

```
npm config set init-author-name 'operezol'
npm config get init-author-name
npm config delete init-author-name
```
Or the shorthand
```
npm set init-author-name 'operezol'
npm get init-author-name
npm config delete init-author-name
```

#### Add packages to package.json with npm

Later packages can be added within the file package.json with the following command.

```
npm install packageName --save
```
or the shorthand
```
npm i packageName -S
```

#### Add package for development environment

```
npm install packageName --save-dev
```
or the shorthand
```
npm i packageName -D
```

#### Add package globaly (for all projects)

```
npm install packageName --global
```
or the shorthand
```
npm i packageName -g
```

### Install nodeunit with npm for to unit testing 

```
npm i -g nodeunit
```

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
    
    test.done();
    
  } 
```

#### Reset Object Tested after each test

```
export["setUp"]=function(callback){
  objectNameToTest.reset(); // has to be declarated on object code
  callback();
}
```

#### Use nodeunit to test entire test folder from node terminal

nodeunit test

### Install express.js to build a web server with npm

npm i -g express

#### Build web server with express

```
var express = require("express");

var app = express();

app.listen(3000);
```

##### Routing with express

```
app.get("/",function(req,res){
  res.send("Hello, world!");
});
app.get("/section",function(req,res){
  res.send("Welcome to section!");
});

```

##### Getting parameters from URL with express

 Given next URL with parameters on it:
 
 localhost:3000/section?parameters=1,2,3,4,5,6
 
```
app.get("/section",function(req,res){
  var parameters = req.query.parameters.split(",");
});

```


