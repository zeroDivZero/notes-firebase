# REALTIME DATABASE

In Build menu on left, choose **Realtime Database**:

![Realtime Database](/assets/realtime-database/rtdb-menu.png)

Create:

![Create Realtime Database](/assets/realtime-database/rtdb-create.png)

Choose location:

![Choose Realtime Database Location](/assets/realtime-database/rtdb-location.png)

Choose **Security Rules** (**test mode** for testing):

![Choose Realtime Database Security Rules](/assets/realtime-database/rtdb-securityrules.png)

Copy reference URL (to be used in code):

![Realtime Database Reference URL](/assets/realtime-database/rtdb-refurl.png)

Code:

```js
import { initializeApp } from //...
import { getDatabase, ref, push } from //...

const appSettings = {
  databaseURL: // reference URL goes here
}

const app = initializeApp(appSettings);
const db = getDatabase(app);
const moviesInDB = ref(db, "movies");

// ...

// push value to ref
push(moviesInDB, "Citizen Kane");
```
