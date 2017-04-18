# AngularRouting

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.0.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive/pipe/service/class/module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).
Before running the tests make sure you are serving the app via `ng serve`.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).


To generate project with routing:

ng new angular-routing --routing -d (dry run)
then...
ng new angular-routing --routing 

run ng serve -o ...to test and see if working...

open 2nd terminal in angular-routing directory..

Create two new components:

ng g c dashboard

ng g c customer

create routes for new components in app-routing.module.ts:

import { DashboardComponent } from "app/dashboard/dashboard.component";
import { CustomerComponent } from "app/customer/customer.component";

const routes: Routes = [
  {path: '', pathMatch:'full', redirectTo: 'dashboard' },
  {path: 'dashboard', component: DashboardComponent},
  {path: 'customer', component: CustomerComponent},
];

----------------

Type nav>ul>li*2 then hit tab to auto create Nav with UL!!!!

Link to components:

 <a href="" [routerLink]="['/dashboard']">Dashboard</a>
 <a href="" [routerLink]="['/customer']">Customer</a>

Add new module:

ng g m admin --routing -d (dry run)
ng g m admin --routing 

Add new components within admin:

ng g c admin

ng g c admin/email-blast 

ng g c admin/users

then go to app.module.ts:

and add in AdminModule (right above AppRoutingModule) + import @ top of page.....

..then in admin-routing.module.ts:

create object with paths + import @ top of file:

  {
    path: 'admin', 
    component: AdminComponent
  }


Create/add router outlet in admin.component.html:

<router-outlet></router-outlet>

In admin-routing.module.ts:

add child component paths + import @ top of file:

children: [
  {path: '', component: UsersComponent},
  {path: 'blast', component: EmailBlastComponent}
]

Creat dist folder:

ng build

then...

npm i source-map-explorer --save-dev

...to see what is in builds...

./node_modules/.bin/source-map-explorer dist/main.bundle.js

./node_modules/.bin/source-map-explorer dist/vendor.bundle.js

run ng build --aot

...then re-run

./node_modules/.bin/source-map-explorer dist/vendor.bundle.js

to see diff in file sizes

ng build -help

run:

ng build --prod  ..for AOT, uglification and tree-shaking

then run:

./node_modules/.bin/source-map-explorer dist/vendor + tab 

...then check other bundles.....etc..

..to see reduction in bundle size....BUT prompt says that there is 
no source map...so to generate prod with map run:

ng build --prod --sm 

------------------

ng serve --help

options:

--open or -o

--port or -p

--live-reload or -lr

--ssl  serving https

--proxy-config or -pc 

------------------------------

EX:

run:
 ng serve -p 8626 -o //change port

 ng serve -p 8626 -o -lr false //without live reload

 ng serve --prod -o //does full prod build in memory + launches in browser...for testing prod build

 To work outside of/cancel CLI:

 run:

 ng eject  //nope!

 --------------------

 Adding Angular material:

 npm i @angular/material --save

 NOTE: if have version "@angular/material": "^2.0.0-beta.3"" also need to install 
 "@angular/animations" --save When full (ie., not beta) version is out, then update

https://material.angular.io/guide/getting-started

 then import in app.module + import in styles.css + add button and icon to app.component.html (from angular/material)


