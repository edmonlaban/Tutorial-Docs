![Image result for angular 4logo](https://cdnhtml5hive.azureedge.net/wp-content/uploads/2017/09/angular-logo.png?x48470)

# ANGULAR 4

## ENVIRONMENT SETUP

To install Angular 4, we will require:

1. Nodejs
2. Npm
3. Angular CLI
4. IDE for writing codes

### NODEJS

To check if nodejs is installed on your system, type node -v in the terminal

`c:\>node -v`

If it does not print anything, install nodejs on your system. To install nodejs, go the homepage <https://nodejs.org/en/download/> of nodejs and install the package based on your OS.



### NPM

Based on your OS, install the required package. Once nodejs is installed, npm will also get installed along with it. To check if npm is installed or not, type npm –v in the terminal. It should display the version of the npm.

`c:\>npm -v`

### ANGULAR CLI

Angular 4 installations are very simple with the help of angular CLI. Visit the homepage <https://cli.angular.io/> of angular to get the reference of the command.

Type **npm install –g @angular/cli**, to install angular cli on your system.

`c:\>npm install -g @angular/cli`



## PROJECT SETUP

To check if the Angular CLI is installed run the following command:

`c:\>ng -v`

![Screenshot (103)](C:\Users\user\Pictures\Screenshots\Screenshot (103).png)

Project Setup:

1. Create directory or folder for the project.

2. To create a project we will use the use the following command:

   `ng new projectname`

3. Import the project into IDE.

   ![Screenshot (104)](C:\Users\user\Pictures\Screenshots\Screenshot (104).png)

   Now that we have the file structure for our project, let us compile our project with the following command:

   `ng serve`

4. Command `ng serve` to build the application and start the web server.

   The web server starts on port 4200. type the following url http://localhost:4200/ in the browser and see the output.

5. If the port 4200 is not available, you can change the port by using the following command:

   `ng serve --host 0.0.0.0 -port 4205`



### Project Folder Structure:

- **e2e** - end to end test folder. Mainly e2e is used for integration testing and helps unsure the application works fine.
- **node_modules** - The npm package installed is node_modules. You can open the folder and see the packages available.
- **src** - This folder is where we will work on the project using Angular 4.



### Project File Structure:

- **.angular-cli.json** - It basically holds the project name, version of cli etc.

- **.editorconfig** - This is the config of the editor.

- **.gitignore** - A .gitignore file should committed into the repository, in order to share the ignore rules with any other users that clone the repository.

- **karma.conf.js** - This is used for unit testing via the protractor. All the information required for the project is provided in karma.conf.js file.

- **package.json** - It tells which libraries will be installed into node_modules when you run npm install.

  In case you need to add more libraries, you can add those over here and run the `npm install`.

- **protractor.conf.js** - This is the testing configuration required for the application.

- **tsconfig.json** - This basically contains the compiler options required during compilation.

- **tslint.json** - This is the config file with rules to be considered while compiling.



### src Folder

#### App

These files are installed by angular-cli by default.

- **app.modules.ts** - If you open the file, you will see the code has reference to different libraries, which are imported. Angular-cli has used these default libraries for the import - angular/core, platform-browser. The names itself explain the usage of the libraries.

They are imported and saved into variables such as declarations, imports, providers, and bootstraps.

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

​		**declarations** - In declarations, the reference to the components is stored. The App component is the 		default component that is created whenever a new project is initiated.

​		**imports** - This will have the modules imported as shown above. At present, BrowserModule is part of 		the imports which is imported from @angular/platform-browser.

​		**providers** - This will have reference to the services created.

​		**bootstrap** - This has the reference to the default component created, i.e., AppComponent.

- **app.component.css** - You can write your css structure over here. Right now, we have added the background color to the div as shown below.

```
.divdetails{
   background-color: #ccc;
}
```

- **app.component.html** - The html code will be available in this file.

  This is the default html code currently available with the project creation.

```
<!--The content below is only a placeholder and can be replaced.-->
<div class = "divdetails">
   <div style = "text-align:center">
      <h1>
         Welcome to {{title}}!
      </h1>
      <img width = "300" src = "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNv
      ZGluZz0idXRmLTgiPz4NCjwhLS0gR2VuZXJhdG9yOiBBZG9iZSBJbGx1c3RyYXRvciAxOS4xLjAsIFNWRyBFe
      HBvcnQgUGx1Zy1JbiAuIFNWRyBWZXJzaW9uOiA2LjAwIEJ1aWxkIDApICAtLT4NCjxzdmcgdmVyc2lvbj0iMS4
      xIiBpZD0iTGF5ZXJfMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaH
      R0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgeD0iMHB4IiB5PSIwcHgiDQoJIHZpZXdCb3g9IjAgMCAyNTAg
      MjUwIiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCAyNTAgMjUwOyIgeG1sOnNwYWNlPSJwcmVzZXJ2
      ZSI+DQo8c3R5bGUgdHlwZT0idGV4dC9jc3MiPg0KCS5zdDB7ZmlsbDojREQwMDMxO30NCgkuc3Qxe2ZpbGw6I0M
      zMDAyRjt9DQoJLnN0MntmaWxsOiNGRkZGRkY7fQ0KPC9zdHlsZT4NCjxnPg0KCTxwb2x5Z29uIGNsYXNzPSJzdD
      AiIHBvaW50cz0iMTI1LDMwIDEyNSwzMCAxMjUsMzAgMzEuOSw2My4yIDQ2LjEsMTg2LjMgMTI1LDIzMCAxMjUsMj
      MwIDEyNSwyMzAgMjAzLjksMTg2LjMgMjE4LjEsNjMuMiAJIi8+DQoJPHBvbHlnb24gY2xhc3M9InN0MSIgcG9pbn
      RzPSIxMjUsMzAgMTI1LDUyLjIgMTI1LDUyLjEgMTI1LDE1My40IDEyNSwxNTMuNCAxMjUsMjMwIDEyNSwyMzAgMj
      AzLjksMTg2LjMgMjE4LjEsNjMuMiAxMjUsMzAgCSIvPg0KCTxwYXRoIGNsYXNzPSJzdDIiIGQ9Ik0xMjUsNTIuMU
      w2Ni44LDE4Mi42aDBoMjEuN2gwbDExLjctMjkuMmg0OS40bDExLjcsMjkuMmgwaDIxLjdoMEwxMjUsNTIuMUwxMj
      UsNTIuMUwxMjUsNTIuMUwxMjUsNTIuMQ0KCQlMMTI1LDUyLjF6IE0xNDIsMTM1LjRIMTA4bDE3LTQwLjlMMTQyLD
      EzNS40eiIvPg0KPC9nPg0KPC9zdmc+DQo=">
   </div>
   <h2>Here are some links to help you start: </h2>
   <ul>
      <li>
         <h2>
            <a target = "_blank" href="https://angular.io/tutorial">Tour of Heroes</a>
         </h2>
      </li>
      <li>
         <h2>
            <a target = "_blank" href = "https://github.com/angular/angular-cli/wiki">
               CLI Documentation
            </a>
         </h2>
      </li>
      <li>
         <h2>
            <a target="_blank" href="http://angularjs.blogspot.ca/">Angular blog</a>
         </h2>
      </li>
   </ul>
</div>
```

- **app.component.spec.ts** - These are automatically generated files which contain unit test for source component.

- **app.component.ts** - The class for the component is defined over here. You can do the processing of the html structure in the .ts file. The processing will include activities such as connecting to the database, interacting with other conponents, routing, services, etc.

  The structure of the file is as follows:

  ```
  import { Component } from '@angular/core';

  @Component({
     selector: 'app-root',
     templateUrl: './app.component.html',
     styleUrls: ['./app.component.css']
  })
  export class AppComponent {
     title = 'app';
  }
  ```



#### Assets

You can save your images, js files in this folder.



#### Environments

This folder has the detials for the production or the dev environment. The folder contains two files:

- environment.prod.ts
- environment.ts

Both files have details of whether the final file should be compiled in the production environment or the dev environment.



The additional file structure of Angular 4 app folder includes the following:

#### favicon.ico

This is a file that is usually found in the root directory of a website.

#### index.html

This is the file which is displayed in the browser.

```
<!doctype html>
<html lang = "en">
   <head>
      <meta charset = "utf-8">
      <title>HTTP Search Param</title>
      <base href = "/">
      <link href = "https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
      <link href = "https://fonts.googleapis.com/css?family=Roboto|Roboto+Mono" rel="stylesheet">
      <link href = "styles.c7c7b8bf22964ff954d3.bundle.css" rel="stylesheet">
      <meta name = "viewport" content="width=device-width, initial-scale=1">
      <link rel = "icon" type="image/x-icon" href="favicon.ico">
   </head>
   
   <body>
      <app-root></app-root>
   </body>
</html>
```

The body has `<app-root></app-root>`. This is the selector which is used in app.component.ts file and will display the details from app.component.html.



#### main.ts

main.ts is the file from where we start our project development. It starts with importing the basic module which we need. Right now if you see angular/core, angular/platform-browser-dynamic, app.module and environment is imported by default during angular-cli installation and project setup.

```
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
   enableProdMode();
}
platformBrowserDynamic().bootstrapModule(AppModule);
```

The **platformBrowserDynamic().bootstrapModule(AppModule)** has the parent module reference **AppModule**. Hence, when it executes in the browser, the file that is called is index.html. Index.html internally refers to main.ts which calls the parent module, i.e., AppModule when the following code executes −

```
platformBrowserDynamic().bootstrapModule(AppModule);
```

When AppModule is called, it calls app.module.ts which further calls the AppComponent based on the boostrap as follows −

```
bootstrap: [AppComponent]
```

In app.component.ts, there is a **selector: app-root** which is used in the index.html file. This will display the contents present in app.component.html.



#### polyfill.ts

This is mainly used for backward compatibility

#### styles.css

This is the style required for the project.

#### test.ts

Here, the unit test cases for testing the project will be handled.

#### tsconfig.app.json

This is used during compilation, it has the config details that need to be used to run the application.

**tsconfig-spec.json**

This helps maintain the details for testing.

#### typings.d.ts

It is used to manage the TypeScript definition.



## COMPONENTS

Major part of the development with angular 4 is done in the components. Components are basically classes that interact with the .html file of the component, which gets displayed on the browser. The file structure has the app components and it consist of the following files:

- app.component.css
- app.component.html
- app.component.spec.ts
- app.component.ts
- app.module.ts

The above file were created by default when we created new project using the angular-cli command.

If you open up the **app.module.ts** file, it has some libraries which are imported and also a declarative which is assigned the appcomponent as follows:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

The declarations include the AppComponent variable, which we have already imported. This becomes the parent component.

Now, angular-cli has a command to create your own component. However, the app component which is created by default will always remain the parent and the next components created will form the child components.

Let us now run the command to create the component.

`ng g component new-cmp`

When you run the above command in the command line, you will receive the following output - 

```
C:\Users\user\Angular4-app>ng g component new-cmp
installing component
   create src\app\new-cmp\new-cmp.component.css
   create src\app\new-cmp\new-cmp.component.html
   create src\app\new-cmp\new-cmp.component.spec.ts
   create src\app\new-cmp\new-cmp.component.ts
   update src\app\app.module.ts
```

Now, if we go and check the file structure, we will get the new-cmp new folder created under the src/app folder.

The following files are created in the new-cmp folder −

- new-cmp.component.css − css file for the new component is created.
- new-cmp.component.html − html file is created.
- new-cmp.component.spec.ts − this can be used for unit testing.
- new-cmp.component.ts − here, we can define the module, properties, etc.

Changes are added to the app.module.ts file as follows:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { NewCmpComponent } from './new-cmp/new-cmp.component';
// includes the new-cmp component we created

@NgModule({
   declarations: [
      AppComponent,
      NewCmpComponent // here it is added in declarations and will behave as a child component
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent] //for bootstrap the AppComponent the main app component is given.
})

export class AppModule { }
```

The new-cmp.components.ts file is generated as follows:

```
import { Component, OnInit } from '@angular/core'; // here angular/core is imported .

@Component({
   // this is a declarator which starts with @ sign. The component word marked in bold needs to be the same.
   selector: 'app-new-cmp', //
   templateUrl: './new-cmp.component.html', 
   // reference to the html file created in the new component.
   styleUrls: ['./new-cmp.component.css'] // reference to the style file.
})

export class NewCmpComponent implements OnInit {
   constructor() { }
   ngOnInit() {}
}
```

If you see the above new-cmp..component.ts file, it creates a new class called NewCmpComponent, which implements `OnInit(). ngOnInit` is called by default when the class is executed.

Now, the app component, which is created by default becomes the parent component. Any component added later becomes the child component.

When we hit the url in the http://localhost:4200/ browser, it first executes the inde.html file which is shown below:

```
<!doctype html>
<html lang = "en">
   <head>
      <meta charset = "utf-8">
      <title>Angular 4App</title>
      <base href = "/">
      <meta name="viewport" content="width = device-width, initial-scale = 1">
      <link rel = "icon" type = "image/x-icon" href = "favicon.ico">
   </head>
   
   <body>
      <app-root></app-root>
   </body>
</html>
```

The above is the normal html file and we do not see anything that is printed in the browser. Take a look at the tag in the body section:

`<app-root></app-root>`

This is the root tag created by the Angular by default. This tag has the reference in the **main.ts** file.

```
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
   enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule);
```

AppModule is imported from the app of the main parent module, and the same is given to the bootstrap Module, which makes the appmodule load.

**app.module.ts** file:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { NewCmpComponent } from './new-cmp/new-cmp.component';

@NgModule({
   declarations: [
      AppComponent,
      NewCmpComponent
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

Here the AppComponent is the name given, i.e., the variable to store the reference of the **app.component.ts** and the same is given to the bootstrap.

**app.component.ts** file:

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project! by Edmon';
}
```

Angular core is imported and referred as the Component and the same is used in the Declarator as:

```
@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})
```

In the declarator reference to the selector, templateurl and styleurl are given. The selector here is nothing but the tag which is placed in the index.html file that se saw above.

The class `AppComponent` has a variable called title, which is displayed in the browser.

The `@Component` uses the `templateUrl` called **app.component.html** which is as follows:

```
<!--The content below is only a placeholder and can be replaced.-->
<div style="text-align:center">
   <h1>
      Welcome to {{title}}.
   </h1>
</div>
```

It has just the html code and the variable title in curly brackets. It gets replaced with the value, which is present in the **app.component.ts** file. This is called binding.

Now that we have created a new component called **new-cmp**. The same gets included in the **app.module.ts** file, when the command is run for creating a new component.

**app.module.ts** has a reference to the new component created.

**new-cmp.component.ts**:

```
import { Component, OnInit } from '@angular/core';
@Component({
   selector: 'app-new-cmp',
   templateUrl: './new-cmp.component.html',
   styleUrls: ['./new-cmp.component.css']
})

export class NewCmpComponent implements OnInit {
   constructor() { }
   ngOnInit() {}
}
```

Here, we have to import core too. The reference of the component is used in the declarator.

The declarator has the selector called **app-new-cmp** and the **templateUrl** and **styleUrl.**

The .html called new-cmp.component.html is as follows;

```
<p>
   new-cmp works!
</p>
```

As seen above, we have the html code, i.e., the p tag. The style is empty we do not need any styling at present. But when we run the project, we do not see anything related to the new component getting displayed in the browser. Let us now add something and the same can be seen in the browser later.

The selector, i.e., **app-new-cmp** needs to be added in the **app.component.html** file as follows:

```
<!--The content below is only a placeholder and can be replaced.-->
<div style="text-align:center">
   <h1>
      Welcome to {{title}}.
   </h1>
</div>

<app-new-cmp></app-new-cmp>
```

When the `<app-new-cmp></app-new-cmp>` tag is added, all that is present in the .html file of the new component created will get displayed on the browser along with the parent component data.

Let us see the **new-cmp.component.html** file and the **new-cmp.component.ts** file:

**new-cmp.component.ts**

```
import { Component, OnInit } from '@angular/core';

@Component({
   selector: 'app-new-cmp',
   templateUrl: './new-cmp.component.html',
   styleUrls: ['./new-cmp.component.css']
})

export class NewCmpComponent implements OnInit {
   newcomponent = "Entered in new component created by Edmon";
   constructor() {}
   ngOnInit() { }
}
```

In the class, we have added one variable called new component and the value is "**Entered in new component created by Edmon**".

The above variable is bound in the **new-cmp.component.html** file as follows:

```
<p>
   {{newcomponent}}
</p>

<p>
   new-cmp works!
</p>
```

Now since we have included the `<app-new-cmp></app-new-cmp>` selector in the **app.component.html** which is the .html of the parent component, the content present in the new component .html file (new-cmp.component.html) gets displayed on the browser.

![Screenshot (105)](C:\Users\user\Pictures\Screenshots\Screenshot (105).png)

Similarly, we can create components and link the same using the selector in the **app.component.html** file as per our requirements.



## MODULE

In Angular refers to a place where you can group the components, directives, pipes, and services, which are related to the application.

Incase you are developing a website, the header, footer, left, center and the right section become part of a module.

To define the module, we can use the **NgModule**. When you create a new project using the Angular -cli command, the ngmodule is created in the **app.module.ts** file by default and it looks as follows:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

The NgModule needs to be imported as follows:

```
import { NgModule } from '@angular/core';
```

The structure for the ngmodule is as shown below :

```
@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
```

It starts with @NgModule and contains an object which has declarations, imports, providers and bootstrap.

### Declaration

It is an array of components created. If any new component gets created, it will be imported first and the reference will be included in declarations as shown below:

```
declarations: [
   AppComponent,
   NewCmpComponent
]
```

### Import

It is an array of modules required to be used in the application. It can also be used by the components in the Declaration array. For example, right now in the @NgModule we see the Browser Module imported. In case your application needs forms, you can include the module as follows:

```
import { FormsModule } from @angular/forms;
```

The import of in the @NgModule will be like the following:

```
imports: [
   BrowserModule,
   FormsModule
]
```



### Providers

This will include the services created.

### Bootstrap

This include the main app component for starting the execution.



## DATA BINDING

We use curly braces {{}} for data binding; this process called interpolation.

The variable in the **app.component.html** file is referred as {{title}} and the value of title is initialized in the **app.component.ts** file and in **app.component.html** as follows:

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})
export class AppComponent {
   title = 'Angular 4 Project!';
   // declared array of months.
   months = ["January", "Feburary", "March", "April", "May", 
            "June", "July", "August", "September",
            "October", "November", "December"];
}
```

The month's array that is shown above is to be displayed in a dropdown in the browser. For this, we will use the following line of code:

```
<!--The content below is only a placeholder and can be replaced. -->
<div style="text-align:center">
   <h1>
      Welcome to {{title}}.
   </h1>
</div>

<div> Months :
   <select>
      <option *ngFor="let i of months">{{i}}</option>
   </select>
   By Edmon!
</div>
```

We have created a normal select tag with option.  In option we have used the **for loop**. The **for loop** is used to iterate over the months' array, which in turn will create the option tag with the value present in the months.

### *ngFor

The syntax **for** in angular is ***ngFor** **= "let I of months"** and to get the value of months we are displaying it in `{{i}}`.

The two curly brackets help the data binding. You declare the variables in **app.component.ts** file and the same will be replaced using the curly brackets.

![](C:\Users\user\Pictures\Screenshots\Screenshot (106).png)

The variable that is set in the **app.component.ts** can be bound with the **app.component.html** using the curly brackets; for example,{{}}.

Example

Let us now display the data in the browser based on condition. Here, we have added a variable and assigned the value as true. Using the if statement, we can hide/show the content to be displayed.

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   //array of months.
   months = ["January", "February", "March", "April",
            "May", "June", "July", "August", "September",
            "October", "November", "December"];
   isavailable = true;   //variable is set to true
}
```

### IF ELSE condition.

Example:

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   //array of months.
   months = ["January", "February", "March", "April",
            "May", "June", "July", "August", "September",
            "October", "November", "December"];
   isavailable = false;
}
```

In this case, we have made the **isavailable** variable as false. To print the **else** condition, we will have to create the **ng-template** as follows:

```
<ng-template #condition1>Condition is invalid</ng-template>
```

The full code looks like this:

```
<!--The content below is only a placeholder and can be replaced.-->
<div style="text-align:center">
   <h1>
      Welcome to {{title}}.
   </h1>
</div>

<div> Months :
   <select>
      <option *ngFor="let i of months">{{i}}</option>
   </select>
</div>
<br/>

<div>
   <span *ngIf="isavailable; else condition1">Condition is valid.</span>
   <ng-template #condition1>Condition is invalid</ng-template>
</div>
```

**If** is used with else condition and the variable used is **condition1**. The same is assigned as an **id** to the **ng-template**, and when the available variable is set to false the text **Condition1 is invalid** in displayed.

### **IF THEN ELSE** condition

Now, we will make the variable **isavailable** as true. In html, the condition is written in the following way:

```
<!--The content below is only a placeholder and can be replaced.-->
<div style="text-align:center">
   <h1>
   Welcome to {{title}}.
   </h1>
</div>

<div> Months :
   <select>
      <option *ngFor="let i of months">{{i}}</option>
   </select>
</div>
<br/>

<div>
   <span *ngIf="isavailable; then condition1 else condition2">Condition is valid.</span>
   <ng-template #condition1>Condition1 is valid</ng-template>
   <ng-template #condition2>Condition2 is invalid</ng-template>
</div>
```

If the variable is true, then **condition1**, else **condition2**. Now, the two templates are created with **id #condition1** and **#condition2**.



## EVENT BINDING

When a user interacts with an application in the form of keyboard movement, a mouseclick, or a mouseover, it generates an event. These events need to be handled to perform some kind of action. This is where event binding comes into picture.

Example:

**app.component.html**

```
<!--The content below is only a placeholder and can be replaced.-->
<div style = "text-align:center">
   <h1>
      Welcome to {{title}}.
   </h1>
</div>

<div> Months :
   <select>
      <option *ngFor = "let i of months">{{i}}</option>
   </select>
</div>
<br/>

<div>
   <span *ngIf = "isavailable; then condition1 else condition2">
      Condition is valid.
   </span>
   <ng-template #condition1>Condition is valid</ng-template>
   <ng-template #condition2>Condition is invalid</ng-template>
</div>
<button (click)="myClickFunction($event)">
   Click Me
</button>
```

in the **app.component.html** file, we have defined a button and added a function to it using the click event.

```
(click)="myClickFunction($event)"
```

The function is defined in the **.ts** file **app.component.ts**

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   //array of months.
   months = ["January", "Feburary", "March", "April",
            "May", "June", "July", "August", "September",
            "October", "November", "December"];
   isavailable = true;
   myClickFunction(event) { 
      //just added console.log which will display the event details in browser on click of the button.
      alert("Button is clicked");
      console.log(event);
   }
}
```

Upon clicking the button, the control will come to the function **myClickFunction** and a dialog box will appear, which displays the Button is clicked.

Let us now add the change event to the dropdown.

The following line of code will add the change event to the dropdown:

```
<!--The content below is only a placeholder and can be replaced.-->
<div style = "text-align:center">
   <h1>
      Welcome to {{title}}.
   </h1>
</div>

<div> Months :
   <select (change) = "changemonths($event)">
      <option *ngFor = "let i of months">{{i}}</option>
   </select>
</div>
<br/>

<div>
   <span *ngIf = "isavailable; then condition1 else condition2">
      Condition is valid.
   </span>
   <ng-template #condition1>Condition1 is valid</ng-template>
   <ng-template #condition2>Condition2 is invalid</ng-template>
</div>

<button (click) = "myClickFunction($event)">Click Me</button>
```

The function is declared in **app.component.ts**:

Example

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   //array of months.
   months = ["January", "Feburary", "March", "April",
            "May", "June", "July", "August", "September",
            "October", "November", "December"];
   isavailable = true;
   myClickFunction(event) {
      alert("Button is clicked");
      console.log(event);
   }
   changemonths(event) {
      console.log("Changed month from the Dropdown by Edmon");
      console.log(event);
   }
}
```

The console message “**Changed month from the Dropdown** **by Edmon"**is displayed in the console along with the event.

Let us add alert message in **app.components.ts** when the value from dropdown is changed:

```
changemonths(event) {
      alert("Changed month from the Dropdown");
   }
```

When the value in dropdown is changed, a dialog box will appear and the following message will be displayed - “**Changed month from the Dropdown**”.



## TEMPLATES



## DIRECTIVES

In angular is a **js** class, which we declared sa **@directive**. We have 3 directives in Angular:

### Component Directives

These form the main class having details of how the component should be processed, instantiated and used at runtime.

### Structural Directives

A structure directive basically deals with manipulating the dom elements. Structural directives have a *  sign before the directive. For example ***ngIf** ang ***ngFor**.

### Attribute Directives

Attribute directives deal with changing the look and behavior of the dom element.



### How to Create Custom Directives

We will create the directive using the command line. The command to create the directive using the command line is:

`ng g directive nameofthedirective`

`ng g directive changeText`



This is how it appears in the command line:

`ng g directive changeText`
`Your global Angular CLI version (1.7.3) is greater than your local`
`version (1.6.5). The local Angular CLI version is used.`

`To disable this warning use "ng set --global warnings.versionMismatch=false".`
  `create src/app/change-text.directive.spec.ts (241 bytes)`
  `create src/app/change-text.directive.ts (149 bytes)`
  `update src/app/app.module.ts (534 bytes)`



The above files, i.e., **chage-text.directive.spec.ts** and **change-text.directive.ts** get created and the **app.module.ts** file is updated.

**app.module.ts:**

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

import { NewCmpComponent } from './new-cmp/new-cmp.component';
import { ChangeTextDirective } from './change-text.directive';

@NgModule({
   declarations: [
      AppComponent,
      NewCmpComponent,
      ChangeTextDirective
   ],

   imports: [
      BrowserModule
   ],

   providers: [],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

The ChangeTextDirective class is included in the declarations in the above file. The class is also imported from the file given below:

**change-text.directive.ts:**

```
import { Directive } from '@angular/core';
@Directive({
   selector: '[changeText]'
})

export class ChangeTextDirective {
   constructor() { }
}
```

The above file has a directive and it also has a selector property. Whatever we define in the selector, the same has to match in the view, where we assign the custom directive.

In the **app.component.html** view, let us add the directive:

```
<div style="text-align:center">
   lt;span changeText >Welcome to {{title}}.</span>
</div>
```

We will write the changes in **change-text.directive.ts** file as follows:

```
import { Directive, ElementRef} from '@angular/core';
@Directive({
   selector: '[ChangeText]'
})

export class ChangeTextDirective {
   constructor(Element: ElementRef) {
      console.log(Element);
      Element.nativeElement.innerText="Text is changed by changeText Directive. ";
   }
}
```

In the above file, there is a class called **ChangeTextDirective** and a constructor, which takes the element of type **ElementRef**, which is mandatory. The element has all the details to which the **ChangeText** directive is applied.

We added **console.log** element. The output of the same can be seen in the browser console. The text of the element is also changed.



## PIPES

Pipes were earlier called filters in Angular 1 and called pipes in Angular 2.

The | character is used to transform data. 

Example:

```
{{ Welcome to Angular 4 | lowercase}}
```

It takes integers, strings, arrays, and date as input separated with **|** to be converted in the format as required and display the same in the browser.

Another Example using pipes:

Here, We want to display the text given to uppercase. This can be done using pipes as follows:

In the **app.component.ts** file, we have defined the title variable.

**app.component.ts**

```
import { Component } from '@angular/core';
@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
}
```

The following line of code is goes in to **app.component.html** file.

```
<b>{{title | uppercase}}</b><br/>
<b>{{title | lowercase}}</b>
```



Angular 4 provides some built-in pipes. the pipes are listed below:

- Lowercasepipe
- Uppercasepipe
- Datepipe
- Currencypipe
- Jsonpipe
- Percentpipe
- Decimalpipe
- Slicepipe

Let us now see how other pipes work.

The following line of code will help us define the required variables in **app.component.ts** file:

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   todaydate = new Date();
   jsonval = {name:'Rox', age:'25', address:{a1:'Mumbai', a2:'Karnataka'}};
   months = ["Jan", "Feb", "Mar", "April", "May", "Jun",
             "July", "Aug", "Sept", "Oct", "Nov", "Dec"];
}
```

We will use the pipes in the **app.component.html** file:

```
<!--The content below is only a placeholder and can be replaced.-->
<div style = "width:100%;">
   <div style = "width:40%;float:left;border:solid 1px black;">
      <h1>Uppercase Pipe</h1>
      <b>{{title | uppercase}}</b><br/>
      
      <h1>Lowercase Pipe</h1>
      <b>{{title | lowercase}}</b>
      
      <h1>Currency Pipe</h1>
      <b>{{6589.23 | currency:"USD"}}</b><br/>
      <b>{{6589.23 | currency:"USD":true}}</b> //Boolean true is used to get the sign of the currency.
      
      <h1>Date pipe</h1>
      <b>{{todaydate | date:'d/M/y'}}</b><br/>
      <b>{{todaydate | date:'shortTime'}}</b>
      
      <h1>Decimal Pipe</h1>
      <b>{{ 454.78787814 | number: '3.4-4' }}</b> // 3 is for main integer, 4 -4 are for integers to be displayed.
   </div>
   
   <div style = "width:40%;float:left;border:solid 1px black;">
      <h1>Json Pipe</h1>
      <b>{{ jsonval | json }}</b>
      <h1>Percent Pipe</h1>
      <b>{{00.54565 | percent}}</b>
      <h1>Slice Pipe</h1>
      <b>{{months | slice:2:6}}</b> 
      // here 2 and 6 refers to the start and the end index
   </div>
</div>
```

### How To Create Custom Pipe

To create a custom pipe, we have created a new ts file. Here, we want to create the **sqrt** custom pipe. We have given the same name to the file and it looks as follows:

**app.sqrt.ts**

```
import {Pipe, PipeTransform} from '@angular/core';
@Pipe ({
   name : 'sqrt'
})
export class SqrtPipe implements PipeTransform {
   transform(val : number) : number {
      return Math.sqrt(val);
   }
}
```

To create a custom pipe, we have to import **Pipe** and **PipeTransform** from **angular/core**. In the **@Pipe** directive, we have to give the name to our pipe, which will be used in our .html file. Since, we are creating the sqrt pipe, we will name is sqrt.

As we proceed further, we have to create the class and the class name is **SqrtPipe**. This class will implement the **PipeTransform**.

The transform method defined the class will take argument as the number and will return the number after taking the square root.

Since we have create a new file, we need to add the same in **app.module.ts**. This done as follows:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

import { NewCmpComponent } from './new-cmp/new-cmp.component';
import { ChangeTextDirective } from './change-text.directive';
import { SqrtPipe } from './app.sqrt';

@NgModule({
   declarations: [
      SqrtPipe,
      AppComponent,
      NewCmpComponent,
      ChangeTextDirective
   ],

   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule { }
```

We have created the **app.sqrt.ts** class. We have to import the same in **app.module.ts** and specify the path of the file. It also has to be included in the declarations as shown above.

Let us now see the call made to sqrt pipe in the **app.component.html** file.

```
<h1>Custom Pipe</h1>
<b>Square root of 25 is: {{25 | sqrt}}</b>
<br/>
<b>Square root of 729 is: {{729 | sqrt}}</b>
```



## Routing

Routing basically means navigating between pages. You have seen many sites with links that direct you to a new page. This can be achieved using routing. Here the pages that we are referring to will be in the form of components.

In the main parent component **app.modute.ts**, we have to now include the router module as shown below:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { RouterModule} from '@angular/router';

import { AppComponent } from './app.component';
import { NewCmpComponent } from './new-cmp/new-cmp.component';
import { ChangeTextDirective } from './change-text.directive';
import { SqrtPipe } from './app.sqrt';
@NgModule({
   declarations: [
      SqrtPipe,
      AppComponent,
      NewCmpComponent,
      ChangeTextDirective
   ],
   imports: [
      BrowserModule,
      RouterModule.forRoot([
         {
            path: 'new-cmp',
            component: NewCmpComponent
         }
      ])
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule { }
```



**import { RouterModule} from '@angular/router'**

Here, The RouterModule is imported from angular/router. The module is included in the imports as shown below:

```
RouterModule.forRoot([
   {
      path: 'new-cmp',
      component: NewCmpComponent
   }
])
```

**RouterModule** refers to the **forRoot** which takes an input as an array, which in turn has the object of the path and the component. Path is the name of the router and component is the name of the class, i.e., the component created. 

Let us now see the component created file:

```
import { Component, OnInit } from '@angular/core';

@Component({
   selector: 'app-new-cmp',
   templateUrl: './new-cmp.component.html',
   styleUrls: ['./new-cmp.component.css']
})

export class NewCmpComponent implements OnInit {
   newcomponent = "Entered in new component created";
   constructor() {}
   ngOnInit() { }
}
```

The highlighted class is mentioned in the imports of the main module.

**new-cmp.component.html**

```
<p>
   {{newcomponent}}
</p>

<p>
   new-cmp works!
</p>
```

Now, we need the above content from the html file to be displayed whenever required or clicked from the main module. For this, we need to add the router details in the **app.component.html**.

```
<a routerLink = "new-cmp">New component</a>

<br />
<br/>
<router-outlet></router-outlet>
```

In the above code, we have created the anchor link tag and given **routerLink** as **"new-cmp"**. This is referred in **app.module.ts** as the path.

When a user clicks **New component**, the page should display the content. For this, we need the following tag - <router link> </router-link>.

The above tag ensures that the content in the **new-cmp.component.html** will be displayed on the page when a user clicks **New component**.

Here, the new-cmp gets appended to the original url, which is the path given the **app.module.ts** and the router-link in the **app.component.html**.

When a user clicks **New component**, the page is not refreshed and the contents are shown to the user without any reloading. Only a particular piece of the site code will be reloaded when clicked. This features helps when we have heavy content on the page and needs to be loaded based on the user interaction. 



## Services

We might come across a situation where we need some code to be used everywhere on the page. It can be for data connection that needs to be shared across components, etc. Services help us achieve that. With services, we can access methods and properties across other components in the entire project.

To create a service, we need to make use of the command line. The command for the same is:

```
ng g service myservice
```



**myservice.service.ts**

```
import { Injectable } from '@angular/core';

@Injectable()
export class MyserviceService {
   constructor() { }
}
```

Here, the Injectable module is imported from the **@angular/core**. It contains the **@Injectable** method and a class called **MyserviceService**. We will create our service function in the class.

Before creating a new service, we need to include the service created in the main parent **app.module.ts**.

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { RouterModule} from '@angular/router';
import { AppComponent } from './app.component';

import { MyserviceService } from './myservice.service';
import { NewCmpComponent } from './new-cmp/new-cmp.component';
import { ChangeTextDirective } from './change-text.directive';
import { SqrtPipe } from './app.sqrt';

@NgModule({
   declarations: [
      SqrtPipe,
      AppComponent,
      NewCmpComponent,
      ChangeTextDirective
   ],
   imports: [
      BrowserModule,
      RouterModule.forRoot([
         {
            path: 'new-cmp',
            component: NewCmpComponent
         }
      ])
   ],
   providers: [MyserviceService],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

 In the service class we will create a function which will display todays date. We can use the same function in the main parent component **app.component.ts** and also in the new component **new-cmp.component.ts**.

Let us now see the how the function looks in the service and how to use it in components.

```
import { Injectable } from '@angular/core';
@Injectable()
export class MyserviceService {
   constructor() { }
   showTodayDate() {
      let ndate = new Date();
      return ndate;
   }
}
```

Let us see how we can access this function in the component class.

```
import { Component } from '@angular/core';
import { MyserviceService } from './myservice.service';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   todaydate;
   constructor(private myservice: MyserviceService) {}
   ngOnInit() {
      this.todaydate = this.myservice.showTodayDate();
   }
}
```





## HTTP Service

Http service will help us fetch external data, post to it, etc. We need to import the http module to make use of the http service. Let us consider an example to understand how to make use of the http service.

To start using the http service, we need to import the module in **app.module.ts** as shown below:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { HttpModule } from '@angular/http';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule,
      BrowserAnimationsModule,
      HttpModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule { }
```



Let us now use the http service in the **app.component.ts**.

```
import { Component } from '@angular/core';
import { Http } from '@angular/http';
import 'rxjs/add/operator/map';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   constructor(private http: Http) { }
   ngOnInit() {
      this.http.get("http://jsonplaceholder.typicode.com/users").
      map((response) ⇒ response.json()).
      subscribe((data) ⇒ console.log(data))
   }
}
```

Let us understand the code above: We need to import http to make use of the service, which done as follows:

```
import { Http } from '@angular/http';
```

In the class **AppComponent**, a constructor is created and the private variable http of type Http. To fetch data, we need to use the get API available with https as follows:

```
this.http.get();
```

It takes the url to be fetched as the parameter as shown in the code.

We will use the test url -  <https://jsonplaceholder.typicode.com/users> to fetch json data. Two operations were performed on the fetched url data map and subscribe. The map method helps to convert the data to json format. To use the map, we need to import the same as shown below:

```
import 'rxjs/add/operator/map';
```

Once the map is done, the subscribe will log the output in the console.

If you see the json objects are displayed in console. The objects can be displayed in the browser too.

For the objects to be displayed in the browser, update the codes in **app.component.html** and **app.component.ts** as follows:

```
import { Component } from '@angular/core';
import { Http } from '@angular/http';
import 'rxjs/add/operator/map';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})
export class AppComponent {
   constructor(private http: Http) { }
   httpdata;
   ngOnInit() {
      this.http.get("http://jsonplaceholder.typicode.com/users").
      map(
         (response) ⇒ response.json()
      ).
      subscribe(
         (data) ⇒ {this.displaydata(data);}
      )
   }
   displaydata(data) {this.httpdata = data;}
}

```

In **app.component.ts** using the subscribe method we will call the display data method and pass the data fetched as the parameter to it.

In the display data method, we will store the data in a variable httpdata. The data is displayed in the browser using for over this httpdata variable, which is done in the **app.component.html** file:

```
<ul *ngFor = "let data of httpdata">
   <li>Name : {{data.name}} Address: {{data.address.city}}</li>
</ul>
```

The object has properties such as id, name, username, email, and address that internally has street, city, etc. and other details related to phone, website, and company. Using the **for** loop, we will display the name and the city details in the browser as shown in the **app.component.html** file.

Let us now add search parameter, which will filter based on specific data. We need to fetch the data based on the search param passed.

Following are the changes done in **app.component.html** and **app.component.ts**.

```
import { Component } from '@angular/core';
import { Http } from '@angular/http';
import 'rxjs/add/operator/map';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})
export class AppComponent {
   title = 'app';
   searchparam = 2;
   jsondata;
   name;
   constructor(private http: Http) { }
   ngOnInit() {
      this.http.get("http://jsonplaceholder.typicode.com/users?id="+this.searchparam).
      map(
         (response) ⇒ response.json()
      ).
      subscribe((data) ⇒ this.converttoarray(data))
   }
   converttoarray(data) {
      console.log(data);
      this.name = data[0].name;
   }
}
```

For the **get api** we will add the search param id = this.searchparam. The searchparam is equal to 2. We need the details of **id=2** from the json file.

**app.component.html**

`{{name}}`

We have consoled the data in the browser, which received from the http; The same is displayed in the browser console. The name from the json with **id=2** is displayed in the browser.



## FORMS

### Template Driven Form

With a template driven form, most of the work is done in the template, and with the model driven form, most of the work is done in the component class.

Let us now consider working on the Template driven form. We will create a simple login form and add the email id, password and submit button in the form. To start with, we need to import to **FormsModule** from @angular/core which is done in **app.module.ts** as follows:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { RouterModule} from '@angular/router';

import { HttpModule } from '@angular/http';
import { FormsModule } from '@angular/forms';
import { AppComponent } from './app.component';

import { MyserviceService } from './myservice.service';
import { NewCmpComponent } from './new-cmp/new-cmp.component';
import { ChangeTextDirective } from './change-text.directive';
import { SqrtPipe } from './app.sqrt';

@NgModule({
   declarations: [
      SqrtPipe,
      AppComponent,
      NewCmpComponent,
      ChangeTextDirective
   ],
   imports: [
      BrowserModule,
      HttpModule,
      FormsModule,
      RouterModule.forRoot([
         {path: 'new-cmp',component: NewCmpComponent}
      ])
   ],
   providers: [MyserviceService],
   bootstrap: [AppComponent]
})

export class AppModule { }
```

So in **app.module.ts**, we have imported the FormsModule and the same is added in the imports array as shown above.

Let us now create our form in the **app.component.html** file.

```
<form #userlogin = "ngForm" (ngSubmit) = "onClickSubmit(userlogin.value)" >
   <input type = "text" name = "emailid" placeholder = "emailid" ngModel>
   <br/>
   <input type = "password" name = "passwd" placeholder = "passwd" ngModel>
   <br/>
   <input type = "submit" value = "submit">
</form>
```

We have created a simple form with input tags having email id, password and the submit button. we have assigned type, name, and placeholder to it.

In template driven forms, we need to create the model form controls by adding the **ngModel** directive and the **name** attribute. Thus, wherever we want Angular access our data from forms, add ngModel to that tag as shown above. Now if we have to read the emailid and passwd, we need to add the ngModel across it.

If you see, we have also added the **ngForm** to the **#userlogin**. the **ngForm** directive needs to be added to the form template that we have created. We have also added function **onClickSubmit** and assigned **userlogin.value** to it. 

Let us now create the function in the **app.component.ts** and fetch the values entered in the form.

```
onClickSubmit(data) {
      alert("Entered Email id : " + data.emailid);
   }
```

In the above **app.component.ts** file, we have defined the function onClickSubmit. When you click on the form submit button, the control will come to the above function.

### Model Driven form

In the model driven form, we need to import the ReactiveFormsModule from @angular/forms and use the same in the imports array.

**app.module.ts**

```
import { ReactiveFormsModule } from '@angular/forms';


imports: [
    ReactiveFormsModule,
]
```

In app.component.ts, we need to import a few modules for the model driven form. for example, **import { FormGroup, Form Control } from '@angular/forms'**.

```
import { Component } from '@angular/core';
import { MyserviceService } from './myservice.service';
import { FormGroup, FormControl } from '@angular/forms';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})
export class AppComponent {
   title = 'Angular 4 Project!';
   todaydate;
   componentproperty;
   emailid;
   formdata;
   constructor(private myservice: MyserviceService) { }
   ngOnInit() {
      this.todaydate = this.myservice.showTodayDate();
      this.formdata = new FormGroup({
         emailid: new FormControl("angular@gmail.com"),
         passwd: new FormControl("abcd1234")
      });
   }
   onClickSubmit(data) {this.emailid = data.emailid;}
}
```

The variable formdata is initialized at the start of the class and the same is initialized with FormGroup as shown above. The variables emailid and passwd are initialized with default values to be displayed in the form. You can keep it blank in case you want to.

We have used formdata to initialized the form values; we need to use the same in the form UI **app.component.html**.

```
<div>
   <form [formGroup]="formdata" (ngSubmit) = "onClickSubmit(formdata.value)" >
      <input type="text" class="fortextbox" name="emailid" placeholder="emailid" 
         formControlName="emailid">
      <br/>
      
      <input type="password" class="fortextbox" name="passwd" 
         placeholder="passwd" formControlName="passwd">
      <br/>
      
      <input type="submit" class="forsubmit" value="Log In">
   </form>
</div>
<p>
   Email entered is : {{emailid}}
</p>
```

In the .html file, we have used formGroup in square bracket for the form; for example [formGroup]="formdata". On Submit, the function is called **onClickSubmit** for which **formdata.value** is passed.

The input tag **formControlName** is used. It is given a value that we have used in the app.component.ts file.

On clicking submit, the control will pass to the function **onClickSubmit**, which is defined in the **app.compnent.ts** file.



### Form Validation

You can use the built-in form validation or also use the custom validation approach. We will use both approaches in the form. With Angular 4 we need to import Validators from **@angular/forms** as shown below:

```
import { FormGroup, FormControl, Validators} from '@angular/forms'
```

Angular has built-in validators such as **mandatory field**, **minlength**, **maxlength**, and **pattern**. These are to be accessed using the Validators module.

You can just add validator or an array of validators required to tell Angular if a particular field is mandatory.

Let us now try the same on one of the input textboxes, i.e., 	email id. For the email id, we have have added the following validation parameters:

- Required
- Pattern Matching

This is how code undergoes validation in **app.component.ts**.

```
import { Component } from '@angular/core';
import { FormGroup, FormControl, Validators} from '@angular/forms';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   todaydate;
   componentproperty;
   emailid;
   formdata;
   ngOnInit() {
      this.formdata = new FormGroup({
         emailid: new FormControl("", Validators.compose([
            Validators.required,
            Validators.pattern("[^ @]*@[^ @]*")
         ])),
         passwd: new FormControl("")
      });
   }
   onClickSubmit(data) {this.emailid = data.emailid;}
}
```

In **Validators.compose**, you can add the list of things you want to validate on the input field. Right now, we have added the **required** and the **pattern** **matching** parameters to take only valid email.

In the **app.component.html**, the submit button is disabled if any of the form inputs are not valid. This is done as follows:

```
<div>
   <form [formGroup] = "formdata" (ngSubmit) = "onClickSubmit(formdata.value)" >
      <input type = "text" class = "fortextbox" name = "emailid" placeholder = "emailid" 
         formControlName = "emailid">
      <br/>
      <input type = "password" class = "fortextbox" name = "passwd" 
         placeholder = "passwd" formControlName = "passwd">
      <br/>
      <input type = "submit" [disabled] = "!formdata.valid" class = "forsubmit" 
         value = "Log In">
   </form>
</div>

<p>
   Email entered is : {{emailid}}
</p>
```

For the submit button, we have added disabled in the square bracket, which is given value - **!formadata.valid**. Thus, if the **formdata.valid** is not valid, the button will remain disabled and the user will not be able to submmit it.

Let us now try custom validation with the same form. For custom validation, we can define our own custom function and add the required details in it. We will now see an example for the same.

```
import { Component } from '@angular/core';
import { FormGroup, FormControl, Validators} from '@angular/forms';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   title = 'Angular 4 Project!';
   todaydate;
   componentproperty;
   emailid;
   formdata;
   ngOnInit() {
      this.formdata = new FormGroup({
         emailid: new FormControl("", Validators.compose([
            Validators.required,
            Validators.pattern("[^ @]*@[^ @]*")
         ])),
         passwd: new FormControl("", this.passwordvalidation)
      });
   }
   passwordvalidation(formcontrol) {
      if (formcontrol.value.length < 5) {
         return {"passwd" : true};
      }
   }
   onClickSubmit(data) {this.emailid = data.emailid;}
}
```

In the above example, we have created a function **passwordvalidation** and the same is used in a previous section in the formcontrol - **passwd: new FormControl("", this.passwordvalidation)**.

In the function we will check if the length of the characters entered is appropriate. If the characters are less than five, it will return with the passwd true as shown as above - **return {"passwd":true};**. If the characters are more than five, it will consider it as valid and the login will be enabled.



## ANIMATIONS

Animations add a lot of interaction between html elements. Animation was also available with angular 2. The difference with Angular 4 is that animation is no more a part of the **@angular/core** library, but is a separate package that needs to be imported in **app.module.ts**.

To start with, we need to import the library as follows:

```
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
```

The **BrowserAnimationsModule** needs to be added to the import array in **app.module.ts** as shown below:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule,
      BrowserAnimationsModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule { }
```

In **app.component.html** we have added the html elements, which are to be animated.

```
<div>
   <button (click)="animate()">Click Me</button>
   <div [@myanimation] = "state" class="rotate">
      <img src="assets/images/img.png" width="100" height="100">
   </div>
</div>
```

For the main div, we have added a button and a div with an image. There is a click event for which the animate  function is called. And for the div, the **@myanimation** directive is added and given the value as state.

Let us see the **app.component.ts** where the animation is defined.

```
import { Component } from '@angular/core';
import { trigger, state, style, transition, animate } from '@angular/animations';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css'],
   styles:[`
      div{
         margin: 0 auto;
         text-align: center;
         width:200px;
      }
      .rotate{
         width:100px;
         height:100px;
         border:solid 1px red;
      }
   `],
   animations: [
      trigger('myanimation',[
         state('smaller',style({
            transform : 'translateY(100px)'
         })),
         state('larger',style({
            transform : 'translateY(0px)'
         })),
         transition('smaller <=> larger',animate('300ms ease-in'))
      ])
   ]
})

export class AppComponent {
   state: string = "smaller";
   animate() {
      this.state= this.state == 'larger' ? 'smaller' : 'larger';
   }
}
```

We have to import the animation function that is to be used in the .ts file as shown above:

```
import { trigger, state, style, transition, animate } from '@angular/animations';
```

Here we have imported trigger, state, style, transition, and animatefrom @angular/animations.

Now, we will add the animations property to the @Component () decorator:

```
animations: [
   trigger('myanimation',[
      state('smaller',style({
         transform : 'translateY(100px)'
      })),
      state('larger',style({
         transform : 'translateY(0px)'
      })),
      transition('smaller <=> larger',animate('300ms ease-in'))
   ])
]
```

Trigger defines the start of the animation. The first param to it is the name of the animation to be given to the html tag to which the animation needs to be applied. The second param are the functions we have imported - state, transition etc.

The **state** function involves the animation steps, which the element will transition between. Right now we have defined two states, smaller and larger. For smaller state, we have given the style **transform:translateY(100px)** and **transform:translateY(0px)**.

Transition function adds animation to the html element. The first argument takes the states, i.e., start and end; the second argument accepts the animate function. The animate function allows you to define, delay, and easing  of a transition.

Let us now see the .html file to see how the transition function works.

```
<div>
   <button (click)="animate()">Click Me</button>
   <div [@myanimation] = "state" class="rotate">
      <img src="assets/images/img.png" width="100" height="100">
   </div>
</div>
```

There is a style property added in the **@component** directive, which centrally aligns the div. Let us consider the following example to understand the same:

```
styles:[`
   div{
      margin: 0 auto;
      text-align: center;
      width:200px;
   }
   .rotate{
      width:100px;
      height:100px;
      border:solid 1px red;
   }
`],
```

Here, a special character [``] is used to add styles to the html element, if any. For the div, we have given the animation name defined in the app.component.ts file.

On the click of a button it calls the animate function, which is defined in the app.component.ts file as foillows:

```
export class AppComponent {
   state: string = "smaller";
   animate() {
      this.state= this.state == ‘larger’? 'smaller' : 'larger';
   }
}
```

The state variable is defined and is given the default value as smaller. The animate function changes the state on click. If the state is larger, it will convert to smaller; and if smaller, it will convert to larger.

Upon clicking the **Click Me** button, the position of the image is chnged.

The transform function is applied in the y direction, which is changed from 0 to 100px when Click Me button is clicked. The image is stored in the **assets/image** folder.



## MATERIALS

Materials offer a lot of built-in modules for your project. Features such as autocomplete, datepicker, slider, menus, grids, and toolbar are available for use with materials in angular 4.

To use material we need to import the package. Angular 2 has also all the above features but they are available as part of the @angular/core module. Angular 4 has come up with a separate module **@angular/materials**. This helps the user to import the required materials.

To start using materials, you need to install two packages - materials and cdk. Material components depend on the animation module for advanced features, hence you need the animation package for the same, i.e., @angular/animations. The package has already been updated in the previous chapter.

```
npm install --save @angular/material @angular/cdk
```

Let us now see the package.json. **@angular/material** and **@angular.cdk** are installed.

```
{
   "name": "angularstart",
   "version": "0.0.0",
   "license": "MIT",
   "scripts": {
      "ng": "ng",
      "start": "ng serve",
      "build": "ng build",
      "test": "ng test",
      "lint": "ng lint",
      "e2e": "ng e2e"
   },
   
   "private": true,
   
   "dependencies": {
      "@angular/animations": "^4.0.0",
      "@angular/cdk": "^2.0.0-beta.8",
      "@angular/common": "^4.0.0",
      "@angular/compiler": "^4.0.0",
      "@angular/core": "^4.0.0",
      "@angular/forms": "^4.0.0",
      
      "@angular/http": "^4.0.0",
      "@angular/material": "^2.0.0-beta.8",
      "@angular/platform-browser": "^4.0.0",
      "@angular/platform-browser-dynamic": "^4.0.0",
      "@angular/router": "^4.0.0",
      "core-js": "^2.4.1",
      "rxjs": "^5.1.0",
      "zone.js": "^0.8.4"
   },
   
   "devDependencies": {
      "@angular/cli": "1.2.0",
      "@angular/compiler-cli": "^4.0.0",
      "@angular/language-service": "^4.0.0",
      "@types/jasmine": "~2.5.53",
      "@types/jasminewd2": "~2.0.2",
      "@types/node": "~6.0.60",
      "codelyzer": "~3.0.1",
      "jasmine-core": "~2.6.2",
      "jasmine-spec-reporter": "~4.1.0",
      
      "karma": "~1.7.0",
      "karma-chrome-launcher": "~2.1.1",
      "karma-cli": "~1.0.1",
      "karma-coverage-istanbul-reporter": "^1.2.1",
      "karma-jasmine": "~1.1.0",
      "karma-jasmine-html-reporter": "^0.2.2",
      
      "protractor": "~5.1.2",
      "ts-node": "~3.0.4",
      "tslint": "~5.3.2",
      "typescript": "~2.3.3"
   }
}
```

We will now import the modules in the parent module - **app.module.ts** as shown below:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { MdButtonModule, MdMenuModule, MdSidenavModule } from '@angular/material';

import { FormsModule } from '@angular/forms';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule,
      BrowserAnimationsModule,
      MdButtonModule,
      MdMenuModule,
      FormsModule,
      MdSidenavModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule { }
```

In the above file, we have imported the following modules from **@angular/material**.

```
import { MdButtonModule, MdMenuModule, MdSidenavModule } from '@angular/material';
```

And the same is used in the imports array as shown below:

```
imports: [
   BrowserModule,
   BrowserAnimationsModule,
   MdButtonModule,
   MdMenuModule,
   FormsModule,
   MdSidenavModule
]
```

The **app.component.ts** is as shown below:

```
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   myData: Array<any>;
   constructor() {}
}
```

Let us now add the material in **app.component.html**.

```
<button md-button [mdMenuTriggerFor]="menu">Menu</button>
<md-menu #menu="mdMenu">
   <button md-menu-item>
      File
   </button>
   <button md-menu-item>
      Save As
   </button>
</md-menu>

<md-sidenav-container class="example-container">
   <md-sidenav #sidenav class="example-sidenav">
      Angular 4
   </md-sidenav>
      
   <div class="example-sidenav-content">
      <button type="button" md-button  (click)="sidenav.open()">
         Open sidenav
      </button>
   </div>
</md-sidenav-container>
```

In the above file, we have added Menu and Sidenav.

### Menu

To add menu, <md-menu></md-menu> is used. The **file** and **Save As** items are added to the button under **md-menu**. There is a main button added **Menu**. The reference of the same is given the <md-menu> by using [mdMenuTriggerFor]="menu" and using the menu with **# in <md-menu>**.

### Sidenav 

To add sidenav, we need **<md-sidenav-container></md-sidenav-container>**. **<md-sidenav></md-sidenav>** is added as a child to the container. There is another div added, which triggers the sidenav by using **(click)="sidenav.open()"**. Following is the display of the menu and the sidenav in the browser.



Let us now add a datepicker using materials. To add a datepicker, we need to import the modules required to show the datepicker.

In **app.module.ts**, we have imported the following module as shown below for datepicker:

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';

import { MdDatepickerModule, MdInputModule, MdNativeDateModule } from '@angular/material';
import { FormsModule } from '@angular/forms';
import { AppComponent } from './app.component';

@NgModule({
   declarations: [
      AppComponent
   ],
   imports: [
      BrowserModule,
      BrowserAnimationsModule,
      FormsModule,
      MdDatepickerModule,
      MdInputModule,
      MdNativeDateModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule { }
```

Here, we have imported modules such as **MdDatepickerModule**, **MdInputModule**, and **MdNativeModule**.

Now the **app.component.ts** is as shown below:

```
import { Component } from '@angular/core';
@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})

export class AppComponent {
   myData: Array<any>;
   constructor() {}
}
```

The **app.component.html** is as shown below:

```
<md-input-container>
   <input mdInput [mdDatepicker]="picker" placeholder="Choose a date">
   <button mdSuffix [mdDatepickerToggle]="picker"></button>
</md-input-container>

<md-datepicker #picker></md-datepicker>
```

