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
* _**node-gyp with Windows 8 and Visual Studio 2012 error during installing package**_ 

    Solution:
    ```cmd
        npm install zombie --python=C:\tools\python27\python.exe --msvs_version=2013
    ```
        Windows 8
        visual studio 2013 (Full version)
* _**cannot use grunt**_ - module is not defined - coffee-script (for example)

    Solution: 
        
    - Remove ```node_modules``` directory.
    - ```npm cache clean``` to empty downloaded temporary dependencies, just in case.
    - ```npm install``` again, and better not to interrupt it while running.
