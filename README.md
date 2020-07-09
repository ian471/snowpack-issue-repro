Repro steps:

```
npm install

npx snowpack build --buildOptions.baseUrl ./
```

This yields the following `build/index.js`:

```js
import {render} from "web_modules/preact.js";

```

Note that the module specifier is invalid. Relative paths have to start with `./` or the browser will fail with an error like:

```
Uncaught TypeError: Failed to resolve module specifier "web_modules/preact.js". Relative references must start with either "/", "./", or "../".
```
