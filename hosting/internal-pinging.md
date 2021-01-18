---
description: >-
  Keep your apps alive with some hosting free providers, by preventing them to
  auto sleep after inactivity.
---

# Internal Pinging

### What is Internal Pinging?

Internal pinging is where the application, keeps itself alive usually at a certain interval, to stop them from sleeping. This is used to **stop apps sleeping** in free hosting services, which can allow for 24/7 hosting, given the right conditions.

* [x] Works on Heroku.com - \(until free dyno hours run out\)
* [x] Works on Glitch.com \(10 hours at a time\)

### 1. Install `node-fetch`

This package is used to send HTTP GET requests to a URL. You can use the package of your choice.

```text
npm i -S node-fetch
```

### 2. Add the Script

This script will send a HTTP GET request to a Heroku app, every 5 minutes. In theory, this will keep it awake until the free dyno hours run out.

#### TypeScript / ES6

```typescript
import fetch from 'node-fetch';

setInterval(() => fetch(`https://<your_app>.herokuapp.com`), 5 * 60 * 1000);
```

#### JavaScript

```javascript
const fetch = require('node-fetch');

setInterval(() => fetch(`https://<your_app>.herokuapp.com`), 5 * 60 * 1000);
```

### 3. Connect Script to Main Application

Make sure to connect the script to the bottom of your main file \(e.g. `app.js`\), and it should do the rest.

#### TypeScript / ES6

```typescript
import './keep-alive';
```

#### JavaScript

```javascript
require('./keep-alive');
```

### Now What?

Your application should stay online for longer, or 24/7, depending on your host.

