# vue-webpack-boilerplate

> A full-featured Webpack setup with hot-reload, lint-on-save, unit testing & css extraction.

### Before You Start...

This boilerplate is targeted towards large, serious projects and contains a lot of moving pieces. If you just want to try out `vue-loader` or whip out a quick prototype, use the [webpack-simple](https://github.com/vuejs-templates/webpack-simple) template instead.

### Usage

This is a project template for [vue-cli](https://github.com/vuejs/vue-cli).

``` bash
$ npm install -g vue-cli
$ vue init webpack my-project
$ cd my-project
$ npm install
$ npm run dev
```

### Folder Structure

``` bash
.
├── build
│   ├── dev-server.js         # development server script
│   ├── webpack.base.conf.js  # shared base webpack config
│   ├── webpack.dev.conf.js   # development webpack config
│   ├── webpack.prod.conf.js  # production webpack config
│   └── ...
├── src
│   ├── main.js               # app entry file
│   ├── App.vue               # main app component
│   ├── components            # ui components
│   │   └── ...
│   └── assets                # module assets (processed by webpack)
│       └── ...
├── static                    # pure static assets (directly copied)
├── dist                      # built files ready for deploy
├── test
│   └── unit                  # unit tests
│       └── ...
│   └── e2e                   # e2e tests
│       └── ...
├── .babelrc                  # babel config
├── .eslintrc.js              # eslint config
├── index.html                # main html file
└── package.json              # build scripts and dependencies
```

### What's Included

- `npm run dev`: first-in-class development experience.
  - Webpack + `vue-loader` for single file Vue components.
  - State preserving hot-reload
  - State preserving compilation error overlay
  - Lint-on-save with ESLint
  - Source maps

- `npm run build`: Production ready build.
  - JavaScript minified with [UglifyJS](https://github.com/mishoo/UglifyJS2).
  - HTML minified with [html-minifier](https://github.com/kangax/html-minifier).
  - CSS across all components extracted into a single file and minified with [cssnano](https://github.com/ben-eb/cssnano).
  - All static assets compiled with version hashes for efficient long-term caching, and a production `index.html` is auto-generated with proper URLs to these generated assets.
  - **To serve built files, run an HTTP server inside `/dist`**.

- `npm run unit`: Unit tests run in PhantomJS with [Karma](http://karma-runner.github.io/0.13/index.html) + [Jasmine](http://jasmine.github.io/) + [karma-webpack](https://github.com/webpack/karma-webpack).
  - Supports ES2015 in test files.
  - Supports all webpack loaders.
  - Easy [mock injection](http://vuejs.github.io/vue-loader/workflow/testing-with-mocks.html).

- `npm run e2e`: End-to-end tests with [Nightwatch](http://nightwatchjs.org/).
  - Run tests in multiple browsers in parallel.
  - Works with one command out of the box:
    - Selenium and chromedriver dependencies automatically handled.
    - Automatically spawns the Selenium server.

For a better understanding of how things work, consult the docs for respective projects listed. In particular, [Webpack](http://webpack.github.io/) and [vue-loader](http://vuejs.github.io/vue-loader).

### Difference between `src/assets/` and `static/`

- Files inside `src/assets/` should be referenced via relative paths inside Vue component templates and styles. They will be processed by `url-loader` and `file-loader` before copied into `/static`.

- Files inside `static/` are copied directly; they can be reference anywhere via root-relative paths that start with `/static/`.

In general you should prefer `src/assets/` as it allows you to leverage loader features such as file naming with hashes and conditional base-64 inline-ing.

### Customizations

You will likely need to do some tuning to suit your own needs:

- Install additional libraries that you need, e.g. `vue-router`, `vue-resource`, `vuex`, etc...

- Use your preferred `.eslintrc` config.

- Add your preferred CSS pre-processor, for example:

  ``` bash
  npm install less-loader --save-dev
  ```

- Working with an existing backend server:

  - Edit `proxyTable` in [`build/dev-server.js`](https://github.com/vuejs-templates/webpack/blob/master/template/build/dev-server.js#L9-L13).

- For unit testing:

  - You can run the tests in multiple real browsers by installing more [karma launchers](http://karma-runner.github.io/0.13/config/browsers.html) and adjusting the `browsers` field in `test/unit/karma.conf.js`.

  - You can also swap out Jasmine for other testing frameworks, e.g. use Mocha with [karma-mocha](https://github.com/karma-runner/karma-mocha).

- For e2e testing:

  - To configure which browsers to run the tests in, edit "test_settings" in `test/e2e/nightwatch.conf.json` and the `--env` flag in `test/e2e/runner.js`. If you wish to configure remote testing on services like SauceLabs, you will need a separate config file. Consult [Nightwatch's docs](http://nightwatchjs.org/guide#selenium-settings) for more details.

### Fork It And Make Your Own

You can fork this repo to create your own boilerplate, and use it with `vue-cli`:

``` bash
vue init username/repo my-project
```
