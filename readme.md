### For typescript compiling
`npm install typescript`


### install angular version 5

`npm install @angular/cli@1.7 -g`

### create new angular project
`ng new angular4-demo`

### navigate to angular4-demo and run the app 
`ng serve`


### it launches the app here http://localhost:4200/

### package.json
* use community developed project
* also to expose self developed code to the community
* dependencies
	 needed at the time of deployment
* dev dependencies
	needed only for development
	
### versioning semver.org

`
x.y.z
1.0.0
| | |
| | |__ patching
| | 
| |____ backward compatible
|
|______ major version and do not support previous
`


### angular-cli.json
* index.html will be the only file served 
* main.ts to load the modules using the library platformBrowserDynamic
* style - global stylesheet

### Two modes dev mode and production mode
* dev - angular cycle run twice
* prod - angular cycle run once
