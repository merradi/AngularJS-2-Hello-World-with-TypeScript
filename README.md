<p>Setup</p><br/>

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

"scripts": {
    "tsc": "tsc -p src -w",
    "start": "live-server --open=src"
}

-p DIRECTORY Compile the project in the given directory
-w Watch input files
src/index.html

<html>
  <head>
    <title>Angular Hello World</title>
    <script src="../node_modules/es6-shim/es6-shim.js"></script>
    <script src="../node_modules/systemjs/dist/system.src.js"></script>
    <script src="../node_modules/angular2/bundles/angular2.dev.js"></script>
    <script>
      System.config({
        packages: {'app': {defaultExtension: 'js'}}
      });
      System.import('app/app');
    </script>
  </head>
  <body>
    <my-app>Loading...</my-app>
  </body>
</html>
src/app/app.ts

import {bootstrap, Component} from 'angular2/angular2';

@Component({
  selector: 'app',
  template: '<h1>Hello world i'm in PARIS</h1>'
})
class AppComponent { }

bootstrap(AppComponent);
src/tsconfig.json

{
  "compilerOptions": {
    "target": "ES5",
    "module": "commonjs",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false
  }
}
