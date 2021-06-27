# Mystore

Trying 3.4/latest by [following these docs](https://sap.github.io/spartacus-docs/building-the-spartacus-storefront-from-libraries-3-4/).

```txt
> ng new mystore --style=scss & cd mystore
> ng add @spartacus/schematics@latest
Installing packages for tooling via yarn.
Installed packages for tooling via yarn.
? Which Spartacus features would you like to set up?
Please note that for most Spartacus features to be properly configured, the Account feature is required. (Press <space> to select, <a> to toggle all, <i> to invert selection)
>(*) Assisted Services Module
 (*) Saved Cart
 ( ) Customer Data Cloud Integration
 ( ) Context-Driven Services Integration
 ( ) Organization - Adminstration (b2b feature)
 ( ) Organization - Order Approval (b2b feature)
 (*) Product - Bulk Pricing
Please note that for most Spartacus features to be properly configured, the Account feature is required. Assisted Services Module, Saved Cart, Product - Bulk Pricing, Produ
ct - Variants, SmartEdit, Store Finder, Tracking - Personalization, User - Account, User - Profile
            ✅️ Added '@spartacus/core' into dependencies
            ✅️ Added '@spartacus/storefront' into dependencies
            ✅️ Added '@spartacus/assets' into dependencies
            ✅️ Added '@spartacus/styles' into dependencies
            ✅️ Added '@angular/common' into dependencies
            ✅️ Added '@angular/core' into dependencies
            ✅️ Added '@angular/platform-browser' into dependencies
            ✅️ Added '@angular/router' into dependencies
            ✅️ Added '@ngrx/effects' into dependencies
            ✅️ Added '@ngrx/router-store' into dependencies
            ✅️ Added '@ngrx/store' into dependencies
            ✅️ Added 'angular-oauth2-oidc' into dependencies
            ✅️ Added 'i18next' into dependencies
            ✅️ Added 'i18next-xhr-backend' into dependencies
            ✅️ Added 'rxjs' into dependencies
            ✅️ Added '@angular/forms' into dependencies
            ✅️ Added '@angular/service-worker' into dependencies
            ✅️ Added '@ng-bootstrap/ng-bootstrap' into dependencies
            ✅️ Added '@ng-select/ng-select' into dependencies
            ✅️ Added 'ngx-infinite-scroll' into dependencies
            ✅️ Added 'bootstrap' into dependencies
            ✅️ Added '@spartacus/asm' into dependencies
            ✅️ Added '@spartacus/cart' into dependencies
            ✅️ Added '@spartacus/product' into dependencies
            ✅️ Added '@spartacus/smartedit' into dependencies
            ✅️ Added '@spartacus/storefinder' into dependencies
            ✅️ Added '@spartacus/tracking' into dependencies
            ✅️ Added '@spartacus/user' into dependencies
CREATE src/app/spartacus/spartacus.module.ts (465 bytes)
CREATE src/app/spartacus/spartacus-features.module.ts (3641 bytes)
CREATE src/app/spartacus/spartacus-configuration.module.ts (979 bytes)
UPDATE package.json (2066 bytes)
UPDATE src/app/app-routing.module.ts (359 bytes)
UPDATE src/app/app.module.ts (706 bytes)
UPDATE src/styles.scss (137 bytes)
UPDATE src/app/app.component.html (32 bytes)
…
CREATE src/app/spartacus/features/smartedit/smart-edit-feature.module.ts (514 bytes)
UPDATE src/app/spartacus/spartacus-features.module.ts (4112 bytes)
UPDATE angular.json (4214 bytes)
√ Packages installed successfully.
√ Packages installed successfully.
```


Configure via the docs which say: *Open the src\app\spartacus\spartacus-configuration.module.ts file, and check for any changes you want to make for your setup.*

baseUrl: Points to your SAP Commerce Cloud server..  In this case, using the training server: https://spartacus-training.eastus.cloudapp.azure.com:8443

Here are some notes whcih were not followed:

```txt
prefix: Defines the prefix for OCC calls.
The default for Spartacus libraries 3.0 and later is /occ/v2/; this entry is not added by schematics.
If using 2005 or later, the default backend prefix is /occ/v2/.
If using 1905, or 2005 with the OCC AddOn, add the line prefix: '/rest/v2/'.
features.level: Defines the compatibility level
context: Defines the site context such as base site, language, and currency.
To see the base site in the URL and add Apparel store support, change context to the following:
 context: {
 urlParameters: ['baseSite', 'language', 'currency'],
 baseSite: ['electronics-spa','apparel-uk-spa'],
 currency: ['USD', 'GBP',]
 },
If using Powertools, add powertools-spa to the list in baseSite.
```

As stated, I didn't do anything else except use the training server.

```txt
>yarn start
yarn run v1.22.10
$ ng serve
Another process, with id 2560, is currently running ngcc.
Waiting up to 250s for it to finish.
(If you are sure no ngcc process is running then you should delete the lock-file at C:/Users/timothy.curchod/repos/sap/mystore/node_modules/@angular/compiler-cli/ngcc/__ngcc_lock_file__.)
….

chunk {main} main.js, main.js.map (main) 77.7 kB [initial] [rendered]
….
chunk {vendor} vendor.js, vendor.js.map (vendor) 9.08 MB [initial] [rendered]
Date: 2021-06-27T04:49:22.301Z - Hash: 1320b5cf576d0e09592a - Time: 48932ms
WARNING in ./src/styles/spartacus/cart.scss (./node_modules/css-loader/dist/cjs.js??ref--13-1!./node_modules/postcss-loader/src??embedded!./node_modules/resolve-url-loader??ref--13-3!./node_modules/sass-loader/dist/cjs.js??ref--13-4!./src/styles/spartacus/cart.scss)
Module Warning (from ./node_modules/postcss-loader/src/index.js):
Warning
(18578:3) start value has mixed support, consider using flex-start instead
** Angular Live Development Server is listening on localhost:4200, open your browser on http://localhost:4200/ **
: Compiled successfully.
```

Site works.

## Original Readme

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 10.2.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
