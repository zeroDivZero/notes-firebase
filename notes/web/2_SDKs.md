# SDKs

Usage of each SDK/service follows similar pattern.

```js
import { getAuth, onAuthStateChanged } from 'firebase/auth';
import { getFirestore } from 'firebase/firestore';

// ... `app` created

const auth = getAuth(app);
const db = getFirestore(app);

// detect auth state
onAuthStateChanged(auth, user => {
  if (user != null) {
    console.log('logged in!');
  } else {
    console.log('no user');
  }
});
```

Each service has *get* function (`getAuth`, `getFirestore`). Takes app as param.

Import each feature as function (`onAuthStateChanged`). Takes service as param.

Same pattern for subpackage. Function's first param is either service or relevant container.

```js
import { getFirestore, collection, getDocs } from 'firebase/firestore';

// ...

const db = getFirestore(app);
const todosCol = collection(db, 'todos');
const snapshot = await getDocs(todosCol);
```

Better pattern than if features were methods of service. Functional approach, more performant. Helps JS module bundler eliminate unused code (*tree shaking*).

## Browser Module

Browser doesn't understand imports, can't run code as is. **Browser module** is native web platform feature to allow import/export code as modules. To try service as browser module, replace import line using pattern:

```js
import { } from 'https://www.gstatic.com/firebasejs/9.18.0/firebase-SERVICE.js'
```

And in html load script with type `module`:

```html
<script type="module" src="/src/index.js"></script>
```

Not recommended for production. Use module bundler instead (better optimization).
