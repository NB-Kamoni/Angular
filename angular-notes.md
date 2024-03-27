## Angular App SetUp

# Genesis

* Have angular cli installed.
* To get the module file you have to select the --standalone false option

```javascript
ng new app-name --standalone false
```

* Generate new pages

```javascript
ng generate component page-one
ng generate component page-two
```

# Routing
* Go to app-routing.module.tsand add the following

```javascript
import { Page-oneComponent } from './page-one/page-one.component'
import { Page-twoComponent } from './page-two/page-two.component'

const routes: Routes = [
    { path: 'page-one', component: Page-one.Component },
    { path: 'page-two', component: Page-two.component },
    { path: '', redirectTo: '/page-one', pathMatch: 'full'} //redirects as homepage
];
```
# Navigation
Go to app.component.html and add navigation

```javascript
<nav>
  <ul>
    <li><a routerLink="/page-one">Dashboard</a></li>
    <li><a routerLink="/page-two">Users</a></li>
  </ul>
</nav>
<router-outlet></router-outlet>
```
# Implement components
Go to page-one.component.html...Add some html

# Serve the application
use the command 
```
ng serve
```

## Angular UI Design

# Genesis
* Install Angular material: material.angular.io
On terminal
```
ng add @angular/material
```
* Install layout components
on terminal

```
ng generate component HeaderComponent
ng generate component SidebarComponent
ng generate component ContentComponent
ng generate component FooterComponent
```
# Design HTML structure for the components above
in header.component.html

```htm
<mat-toolbar color="primary">Dashboard Header</mat-toolbar>
```
in sidebar.component.html

```htm
<mat-sidenav-container>
  <mat-sidenav mode="side" opened>Sidebar Content</mat-sidenav>
</mat-sidenav-container>
```
in footer.component.html

```htm
<mat-toolbar color="primary">Dashboard Footer</mat-toolbar>
```
# Arrange the components above in the parent component
Eg home page in page-one.component.html: The names eg app-header should be confirmed in header.component.ts>>selector

```htm
<app-header></app-header>
<app-sidebar></app-sidebar>
<mat-sidenav-content>
  <app-content></app-content>
</mat-sidenav-content>
<app-footer></app-footer>
```
# Import angular material module
In the angular module file (app.module.ts)
```javascript

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { MatButtonModule } from '@angular/material/button';
import { MatToolbarModule } from '@angular/material/toolbar';
import { MatSidenavModule } from '@angular/material/sidenav';
import { MatInputModule } from '@angular/material/input';
import { MatCardModule } from '@angular/material/card';

import { AppComponent } from './app.component';
import { HeaderComponent } from './header/header.component';
import { SidebarComponent } from './sidebar/sidebar.component';
import { ContentComponent } from './content/content.component';
import { FooterComponent } from './footer/footer.component';

@NgModule({
  declarations: [
    AppComponent,
    HeaderComponent,
    SidebarComponent,
    ContentComponent,
    FooterComponent
  ],
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    MatButtonModule,
    MatToolbarModule,
    MatSidenavModule,
    MatInputModule,
    MatCardModule
    // Other Angular Material modules as needed for other components
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

