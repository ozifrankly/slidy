[Para ver em Português clique aqui](README-PT.md)

# Slidy

This CLI consists of a way to assemble your project structured by modules, pages, repositories, widgets always following the standards of good practices that has been applied by the community flutter in bigger and more structured projects.
It also provides the libraries manager (libs or pubs) with it you can install multiple libraries with just one command line and even remove and update.

# Migration from v0.2.1 to v1.0.0:

some commands have been improved for ease of usability
for example the module, page and widget generation command have been shortened

```
//vesion 0.2.1
slidy generate module page/search/search

//version 1.0.0
slidy generate module page/search
```

The main folder is no longer called "src" but "app"

## Motivations

We realized that the lack of a project pattern is affecting the productivity of several developers at that initial moment, so we are proposing a development pattern along with a tool that imitates NPM (NodeJS) functionality as well as template generation capabilities (similar to Scaffold ).

## About the Proposed Pattern.

We adopted the BLoC standard for business rule in a structure similar to MVC, where a page or widget has one or more BLoC to manage its business rule.

We are using the module structure and dependency injection of the package [bloc_pattern](https://pub.dev/packages/bloc_pattern). Read the bloc_pattern README to familiarize yourself with the concept of dependency injection, BLoC Provider and modules.


For services and provider we use the **Repository Pattern**.

In this way our folder structure is organized into local modules and a global module, as well as models, repositories and BLoC`s that can be accessed throughout the application in the shared folder.

Sample folder structure generated by **slidy**:

![Folder example](https://github.com/Flutterando/slidy/blob/master/folder.png?raw=true)

## Installation

- You need to have the Dart SDK installed. If you do not have [download now](https://dart.dev/get-dart).
- Now just activate the slidy using the pub:

```
pub global activate slidy
```
- Type  ` slidy --version` -  if you return the slidy version you can consider the complete installation.
- To update the slidy just use the command:
```
slidy upgrade
```

Ready now you can enjoy this new world.

## Commands:    
  **start:** 
     Create a basic structure for your project (confirm that you have no data in the "lib" folder).
```  
slidy start
```     

 **run:** 
     Run scripts placed in the "scripts" parameter in pubspect.yaml
```  
slidy run open_folder
```   
![Folder example](https://github.com/Flutterando/slidy/blob/master/scripts.png?raw=true)

**Install:**
Install (or update) a new package or packages:
```
slidy install rxdart dio bloc_pattern
```
You can also install a package as dev_dependency using the flag --dev
```
slidy i flutter_launcher_icons --dev
``` 
remove a package
 ```
 slidy uninstall dio 
 ```
You can also remove a dev_dependency using the flag --dev


## Generate:

Create a module, page, widget or repository according to the option.
    
**Options:**
    
Creates a new module with **slidy generate module**:
``` 
slidy generate module manager/product
``` 

Creates a new page and its respective Bloc
```
slidy generate page manager/product/pages/add_product
``` 
            
Creates a new widget and its respective Bloc:
```
slidy generate widget manager/product/widgets/product_detail
``` 
NOTE: You can create a page or widget with your respective BLoC using the flag **-b**
            
Create a new repository
```
slidy g r manager/product/repositories/product
``` 


## Common errors:

**Windows:** 

  ![Folder example](/error_windows_install.jpg)

  If you find out with the above error, when trying to run or the ```pub global activate slidy```, then you will have to put in the environment variables manually:

  Go to windows search and search for:  ```Edit System variable```

  After click in ```Environment Variables```

  Search for```Path```

  Then click in New and add the path that appeared on your console in case here is : ```C:\Users\1513 MX5-7\AppData\Roaming\Pub\Cache\Bin``` after that just restart your CMD.




For more details https://t.me/flutterando

