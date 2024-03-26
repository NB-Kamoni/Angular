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
* Go to app-routing.module.ts

```javascript
import { Page-oneComponent } from './page-one/page-one.component'
import { Page-twoComponent } from './page-two/page-two.component'

const routes: Routes = [];
```