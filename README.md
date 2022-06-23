# Create Angular + AngularJS Hybrid
Inspired by [@joelbinn](https://github.com/joelbinn) [tutorial](https://joelbinn.gitbooks.io/hybrid-angular-angularjs-application-with-angular/content/) and [repository](https://github.com/joelbinn/angular-phonecat-hybrid); having the need to move an AngularJS project to an Angular one, here are the steps i followed.

LAST UPDATE: 20220623

### Requirements
- AngularJS source coded following the standards mentioned [here](https://angular.io/docs/ts/latest/guide/upgrade.html#preparation)
- having angular CLI installed globally

### Useful links
- [Angular Upgrade Tutorial / Preparation](https://angular.io/docs/ts/latest/guide/upgrade.html#preparation)
- [Angular Upgrade Tutorial / Upgrading with The Upgrade Module](https://angular.io/docs/ts/latest/guide/upgrade.html#upgrading-with-the-upgrade-module)
- [Hybrid Angular+AngularJS application with Angular CLI](https://joelbinn.gitbooks.io/hybrid-angular-angularjs-application-with-angular/content/)

## Procedure
1. have the AngularJS source in a `src` folder
   ```bash
   git clone _REPO_LINK_ ajs
   ```
2. create a new folder for the new main project (ex. `hybring`)
   ```bash
   ng new hybring
   ```
3. copy AngularJS `src` content in a new subfolder (ex. `app-ajs`) inside the Angular `src` folder (ex. `hybring/src`)
   ```bash
   cp ajs/src hybring/src/app-ajs -r
   ```
4. move to the Angular folder
   ```bash
   cd hybring
   ```
5. install AngularJS dependencies and relative `@types/*`
   ```bash
   npm i -S @angular/upgrade angular angular-resource angular-route
   npm i -D @types/angular @types/angular-resource @types/angular-route
   ```

6. change the extension of all `.js` files to `.ts`
   ```bash
   npm i -g renamer && renamer --find '.js' --replace '.ts' 'src/app-ajs/**/*.js'
   ```
