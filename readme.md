NodeGit-Kit
-----------

An incomplete set of NodeGit helper promises. Please don't use this in production yet.

![NodeGit-Kit example log](https://raw.github.com/thisconnect/nodegit-kit/master/log.png)

Comments are welcome: https://github.com/thisconnect/nodegit-kit/issues

```javascript
var kit = require('nodegit-kit');

var open = kit.open;
var commit = kit.commit;
var diff = kit.diff;
var log = kit.log;
var status = kit.status;

open('../repo-path/new/or/existing')
.then(function(repo){
    return repo;
})
.then(function(repo){
     // git diff
    return diff(repo)
    .then(function(diff){
        // console.log(diff);
        return repo;
    });
})
.then(function(repo){
    // git commit -am"commit message"
    return commit(repo);
})
.then(function(repo){
    // git log
    return log(repo);
})
.then(function(log){
    // console.log(log);
})
.catch(function(error){
    console.error(error.stack);
});
```


```javascript
open('../repo-path/new/or/existing')
.then(function(repo){
     // git status
    return status(repo)
    .then(function(status){
       console.log(status);
       return repo;
    })
})

```
