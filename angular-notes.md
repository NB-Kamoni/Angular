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
