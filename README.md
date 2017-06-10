# DevCampWAP-PAO
Performance Analysis &amp; Optimization

## Performance Tips - Javascript Best Practices
1. go into the `perf-tips/js-best-practices`
2. make a branch `answer/yourname`
3. make a folder under js-best-practices
4. name the folder with your name. ex) `jangkeehyo`
5. create a file named `answer.js` and answer the questions
6. make a pull request to the master

## Gzip Compression - Node.js
1. go into `gzip-nodejs` folder
2. run these commands in order

```
npm install
node server.js
```

3. check out how Gzip works in the web resources

## Page Insights

## Lighthouse

## Gulp
1. Install gulp global

```
npm i -g gulp
```

2. Create a package.json

```
npm init
```

3. Create a gulpfile.js

#### Example 1 - Initial Setup & .task()
- Install node modules using the command below

```
npm install
```

#### Example 2 - .src() & .dest() & gulp-htmlmin

#### Example 3 - .watch() & eslint-google

#### Example 4 - compression sample

#### Example 5 - [Google Starter Kit](https://developers.google.com/web/tools/starter-kit/?hl=ko)

## Webpack
#### Getting-Started
1. Install webpack global

  ```js
  npm i webpack -g
  ```

2. create a package json file

  ```text
  npm init -y
  ```

3. create index.js & index.html

  ```html
  <!-- index.html -->
  <html>
    <head>
      <title>webpack 2 demo</title>
      <script src="https://unpkg.com/lodash@4.16.6"></script>
    </head>
    <body>
      <script src="app/index.js"></script>
    </body>
  </html>
  ```

  ```js
  // index.js
  function component () {
    var element = document.createElement('div');

    /* lodash is required for the next line to work */
    element.innerHTML = _.join(['Hello','webpack'], ' ');

    return element;
  }

  document.body.appendChild(component());
  ```

4. add the contents below into the file

  ```js
  // index.js
  // import & export is ES6 that doesn't work in the browser
  // but webpack would replace them with compatible wrapper code
  + import _ from 'lodash';
  ```

  ```html
  - <script src="https://unpkg.com/lodash@4.16.6"></script>
  - <script src="app/index.js"></script>
  + <script src="dist/bundle.js"></script>
  ```

5. run this command `webpack app/index.js dist/bundle.js` and start the index.html

  ```html
  Hello webpack
  ```

6. Let's add config file for more complex configuration

  ```js
  // webpack.config.js
  // `webpack` command will pick up this config setup by default
  var path = require('path');

  module.exports = {
    entry: './app/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'dist')
    }
  };
  ```

#### Example 1 - CSS Code Splitting
- As for CSS files, use `css-loader`for default setting. The extra option `ExtractTextWebpackPlugin` is available for better performance

```text
npm i css-loader style-loader --save-dev
npm i extract-text-webpack-plugin --save-dev
```

#### Example 2 - Libraries Code Splitting
- When using a couple of libraries, should you import them at the very beginning of bundling all files to avoid repetitively use them in every build.

```text
npm install --save moment
npm install --save lodash

npm i webpack-manifest-plugin --save-dev
```

#### Example 3 - Webpack Dev Server Setting
- Initial development setting to make the build process easier

```
npm install --save-dev webpack-dev-server
webpack-dev-server --open
```

- or add this option to `package.json` to launch the dev server

```json
"scripts": { "start": "webpack-dev-server" }
```

#### Example 4 - Webpack Dev Middleware
- TBD

#### Example 5 - Webpack Plugins
-
