# `initializeApp`

After creating app in Console, should get config. In JavaScript, import needed Firebase product SDKs and use config to create app and services.

```js
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
// TODO: add SDKs for Firebase products
// https://firebase.google.com/docs/web/setup#available-libraries

const firebaseConfig = {
  apiKey: "BlahBlahBlah",
  authDomain: "xyz.firebaseapp.com",
  projectId: "xyz",
  storageBucket: "xyz.appspot.com",
  messagingSenderId: "123456789123",
  appId: "1:123456789123:web:xyzxyzxyz",
  measurementId: "A-BCD2EFG3HI"
};

// initialize Firebase
const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);
```

Safe to include config on client side. Use security rules and App Check to secure.
