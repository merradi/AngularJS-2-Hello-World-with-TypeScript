<p><h1>Setup</h1></p><br/>

git clone git@github.com:merradi/AngularJS-2-Hello-World-with-TypeScript.git<br/>
		  

npm init -y<br/>
npm i typescript<br/>
npm i angular2<br/>
npm i systemjs<br/>
npm i live-server<br/>
npm install es6-shim --save<br/>


Package installés:<br/>

angular2<br/>
systemjs module system<br/>
typescript typescipt compiler<br/>
live-server hot reload<br/>
es6-shim (opti) Angular 2 requires ES6 support<br/>
package.json<br/>

"scripts": {<br/>
    "tsc": "tsc -p src -w",<br/>
    "start": "live-server --open=src"<br/>
}<br/>

-p DIRECTORY Compile the project in the given directory<br/>
-w Watch input files<br/>
src/index.html<br/>

<html><br/>
  <head><br/>
    <title>Angular Hello World</title><br/>
    <script src="../node_modules/es6-shim/es6-shim.js"></script><br/>
    <script src="../node_modules/systemjs/dist/system.src.js"></script><br/>
    <script src="../node_modules/angular2/bundles/angular2.dev.js"></script><br/>
    <script><br/>
      System.config({<br/>
        packages: {'app': {defaultExtension: 'js'}}<br/>
      });<br/>
      System.import('app/app');<br/>
    </script><br/>
  </head><br/>
  <body><br/>
    <my-app>Loading...</my-app><br/>
  </body><br/>
</html><br/>

<p>src/app/app.ts</p><br/>

import {bootstrap, Component} from 'angular2/angular2';<br/>

@Component({<br/>
  selector: 'app',<br/>
  template: '<h1>Hello world i'm in PARIS</h1>'<br/>
})<br/>
class AppComponent { }<br/>

bootstrap(AppComponent);<br/>
src/tsconfig.json<br/>

{<br/>
  "compilerOptions": {<br/>
    "target": "ES5",<br/>
    "module": "commonjs",<br/>
    "sourceMap": true,<br/>
    "emitDecoratorMetadata": true,<br/>
    "experimentalDecorators": true,<br/>
    "removeComments": false,<br/>
    "noImplicitAny": false<br/>
  }<br/>
}<br/>
