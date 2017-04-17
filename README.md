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

 <li><a href="" [routerLink]="['/dashboard']">Dashboard</a></li>
 <li><a href="" [routerLink]="['/customer']">Customer</a></li>

