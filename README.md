# example-private-dep
Minimum requirement for linking a private github repository package as dependency in your project.

### Contents

This is `minimum requirement` contents of the `package.json` in order to include private npm mudules via git repositories:

```json
{
  "name": "myapp",
  "version": "1.0.0",
  "description": "My App",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "rebuild": "rm -fr node_modules/; npm install",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "sdk-core": "git@github.com:hirefirst/sdk-core.git",
    "md5": "^2.2.1"
  }
}
```
### Access to repository

Access to `github` should be granted to user that runs `npm install` via `SSH` keys.
See this [link](https://help.github.com/articles/connecting-to-github-with-ssh/) for detail.

### Using in code

Our custom `module` can be included in your code by using:

```javascript
let mymodule = require('sdk-core'); // sdk-core is the very name of our module

```
