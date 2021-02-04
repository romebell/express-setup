# Express Set up
This is a repo for setting up an express app

## Terminal Commands

```text
10594  cd express-setup
10596  ls
10597  npm init -y
10598  ls
10599  touch index.js
10600  echo "node_modules/" >> .gitignore
10601  ls -a
10602  npm i express ejs express-ejs-layouts axios sequelize pg dotenv
10603  ls
10604  code .
10605  npm i method-override
10606  node index.js
```
## Top 5

```js
// 1 - environment
require('dotenv').config();
```

```js
// 2 - imports
const express = require('express');
const axios = require('axios');
const ejsLayouts = require('express-ejs-layouts');
const methodOverride = require('method-override');
```

```js
// 3 - App set up
const app = express();
app.set('view engine', 'ejs');
```

```js
// 4 - App Middleware (app.use)
app.use(ejsLayouts);
app.use(express.urlencoded({ extended: false }));
app.use(methodOverride('_method'));
```

```js
// 5 - Routes (controllers)
app.get('/', (req, res) => {
    res.send('Welcome to my App'); // Yo, Rome: what is this doing?
});
```

### Listen on a `PORT`
```js
const PORT = process.env.PORT || 8000;
app.listen(PORT, () => {
    console.log(`Server running on PORT: ${PORT}`);
});
```
