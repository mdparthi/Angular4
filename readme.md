### For typescript compiling
`npm install typescript`


### install angular version 5

`npm install @angular/cli@1.7 -g`

### create new angular project
`ng new angular4-demo`

### navigate to angular4-demo and run the app 
`ng serve`

* it launches the app here http://localhost:4200/

### package.json
* use community developed project
* also to expose self developed code to the community
* dependencies
	 needed at the time of deployment
* dev dependencies
	needed only for development
	
### example of versioning https://semver.org/

```
x.y.z
1.0.0
| | |
| | |__ patching
| | 
| |____ backward compatible
|
|______ major version and do not support previous
```



### angular-cli.json
* index.html will be the only file served 
* main.ts to load the modules using the library platformBrowserDynamic
* style - global stylesheet

### Two modes dev mode and production mode
* dev - angular cycle run twice
* prod - angular cycle run once

* AppModule - RootModule usually loads the root component to the application
* Each module can have own directive, services and pipes


* NgModule
	* declarations
		* Pipe
		* Directive
		* Component
	* imports
		* Modules
	* providers
		* register the 
	* bootstrap
		* load the component for which the selector is avilable over the index
		
### create new component

`ng generate component user`

```
  create src/app/user/user.component.html (23 bytes)
  create src/app/user/user.component.spec.ts (614 bytes)
  create src/app/user/user.component.ts (261 bytes)
  create src/app/user/user.component.css (0 bytes)
  update src/app/app.module.ts (390 bytes)
```
  
### Components

* controls a patch of screen
* Passing data into components
	* property binding - syntax - [] also {{}} expression binding
	* event binding - syntax - ()
	* two way data binding - no default support 
	* to achieve two way binding we club both [] ()

### Add bootstrap library
`npm install bootstrap@3 --save`

* use angular-cli.json to include bootstrap 

```
"styles": [
        "../node_modules/bootstrap/dist/css/bootstrap.min.css",
        "styles.css"
      ]
```

* Example of attribute one way binding fromt the user model
	* <img [src]="user.image" class="img-responsive img-rounded">

### Explicit property binding + event binding
	
```
<input type="number" 
              [value]="user.votes"
              (change)="user.votes=$event.target.value">
```

### [(ngModel)] - syntax known as banana in the box
	* property binding + event binding

# Two way binding can be achieved using ngModel

```
<input type="number" [(ngModel)]="user.votes">
```

### Nested Components
* Data Projection -> Parent Component to Child Component
* @Input + Property Binding

* Data Projection
	* <ng-content> </ng-content> child componenet will receive parent component data
	
	```
	<app-user>
	  <header> Header Info </header>
	  <main> Main Info</main>
	  <footer class="footer-sec">Footer Info</footer>
   </app-user>
	```
	
	```
	<div class="container">
    <ng-content select=".footer-sec" ></ng-content>
	</div>
	```
* @Input
	
	* app.component.ts
	
	```
	<app-user [title]="title">
	```
	
	* user.component.ts
	``` import { Component, OnInit, `Input` } from '@angular/core';```
	
	```
	export class UserComponent implements OnInit {
	@Input('title') title : string;
	```
	
	* user.component.html
	```
	 User {{title}} works
	```
	
* Smart Componet - root component sends to child component
* Dump Component / Presentational component - for populating the UI

### Component lifecycle

* ngOnChanges - whenever changes in input data property, which will accept parameter of changes
* ngOnInit - when components loaded  initalized in the browser only once
* ngDoCheck  - when change in data binding
* ngAfterContentInit - when it recieves content using ng-content
* ngAfterContentChecked - 
* ngAfterViewInit - 
* ngAfterViewChanged - 
