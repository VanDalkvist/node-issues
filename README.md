# node-issues
A list of possible node issues

* _**An issue with module name.**_ Name of module register dependence. You can see it when you want to setup your module extensions on the bootstrapping your app. If you will try to get module with ```require('ModuleName')``` - it is not the same as ```require('moduleName')```.

* _**Issue with asynchronous logger and ```process.exit```**_ - When you put message into log source and then exit from application you need to use next pattern: 
    ```
    var exitCode = -1; // 0, 1... 
    logger.log('message');
    setTimeout(function () {
      process.exit(exitCode);
    }, 100);
    ```
 
