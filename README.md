# nodejs-import-export
How to use import/export of es6 in nodejs using babel

### Why?
In some cases, we need to use isomorphic code that are shared between
client and side server, in this case is react and nodejs.  
Let's say we want to do the server side rendering, so we need import 
react components on nodejs/server side. Since react components is jsx
and they use es6 module (import/export), in order to use it, we need 
to compile nodejs by babel to use import/export.  
  
### How?
Install `npm install --save babel-register`.  
Install babel preset es2015 to use es6 in nodejs by `npm install --save-dev babel-preset-es2015`.  
Create `.babelrc` files and add it (recommended).  
```
{
  "presets": ["es2015"]
}
```
Create an entry file, let's say it is `index.js`. Note that in entry file, 
we need to `require('babel-register')` on the very top of that file and we're
not able to use neither `import` or `export`.
Then in the entry file, all the `required files` can use `import` and `export`
