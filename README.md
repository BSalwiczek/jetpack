<p align="center">
  <img src="https://user-images.githubusercontent.com/324440/48484676-a1690280-e80e-11e8-9835-14c6b0c5bb98.png" alt="jetpack" title="jetpack">
</p>

<h4 align="center">Webpack made more convenient.</h4>
<br />

**Jetpack wraps webpack** to create a smoother developer experience. Jetpack can be used instead of webpack, webpack-cli, webpack-dev-server and webpack-dev-middleware without writing any configuration. Jetpack is a thin wrapper around webpack, and can be extended with any of the webpack configuration.

- **Sensible defaults** to handle modern JavaScript, CSS and images.
- **Preconfigured Babel** with `@babel/preset-env` and `@babel/preset-react`, configurable via `.babelrc`.
- **Preconfigured PostCSS** with `postcss-preset-env` including autoprefixing, configurable via `postcss.config.js`.
- **CSS modules available** by switching one config flag.
- **Sass support** by installing `node-sass`.
- **Automatic JSX detection** switches between `React.createElement` or `h` depending on dependencies.
- **Hot reloading built in** for React as well as vanilla JavaScript and CSS.
- **Automatic chunk splitting** with inlined runtime and HTML generation.
- **Smooth workflow** for simultaneously developing client and server applications.
- **Single dependency** with hassle-free updates.
- **Optionally run anywhere** without installing locally, just like `nodemon`.

**Why use jetpack?** To avoid rolling your own custom webpack config or having to paste it from old projects. Jetpack has a set of defaults that should get you off the ground quickly. And with the `proxy` config or universal `jetpack/serve` middleware you don't have to worry about wiring up webpack dev middleware or dev server – everything _just works_.

## Usage

Install globally or locally:

    $ npm install -g jetpack

In your project with `package.json` or `index.js`, start your app on `http://localhost:3030`:

    $ jetpack

To build the app for production to a `dist` directory:

    $ jetpack build

Inspect the bundle size and make up:

    $ jetpack inspect

## Use jetpack anywhere, anytime

One of jetpack goals is to help you run any piece of JavaScript in a browser as easily as it is to run node scripts. Install jetpack globally and point it to any file on your machine. This is an alternative to jsfiddle / codepen / codesandbox style of hacking on things.

    $ jetpack ~/Desktop/magic.js

Or any project on your machine:

    $ jetpack --dir ~/projects/manyverse

## Use jetpack with an API

Another goal of jetpack is to assist you in building complete, production apps. Very often in addition to developing the clientside application, you are also developing an API. Jetpack has a few features to make building such apps easier.

Point your `package.json#main` to your server entry and `package.json#browser` to your client entry.

Now you can run your API server together with jetpack in a single command:

    $ jetpack -x

Alternatively, specify any command to execute:
    $ jetpack -x 'nodemon ./api'

Use this even if your server is not written in node

    $ jetpack -x 'rails s'

Jetpack provides an ability to proxy requests to your api by specifying `proxy` configuration in `jetpack.config.js` or mounting the dev server to your application server using the `jetpack/serve` middleware. Read more about it in [Workflow and deployment](./docs/06-workflow-and-deployment.md) docs.

## Documentation

* [All configuration options](./docs/01-configuration-options.md)
* [Customizing Webpack](./docs/02-customizing-webpack.md)
* [Customizing Babel](./docs/03-customizing-babel.md)
* [Customizing PostCSS](./docs/04-customizing-postcss.md)
* [Customizing Browserslist](./docs/05-customizing-browserslist.md)
* [Workflow and deployment](./docs/06-workflow-and-deployment.md)
* [Hot reloading](./docs/07-hot-reloading.md)
* [Comparison to cra, pwa-cli, parcel, etc.](./docs/08-comparison.md)

#### Recipes

* [Deploying to Netlify](./docs/recipe-01-deploying-to-netlify.md) – static apps
* [Deploying to Now](./docs/recipe-02-deploying-to-now.md) – client and server all in one
* [Deploying to Netlify + Now](./docs/recipe-03-deploying-to-netlify-plus-now.md) – client and server separated
* [Adding Flow](./docs/recipe-04-adding-flow.md)
* [Adding Typescript](./docs/recipe-05-adding-typescript.md)
* [Server side rendering](./docs/recipe-06-server-side-rendering.md)

## Your feedback!

This project is an exploration of some ideas accumulated over a few years using webpack in a variety of projects. Webpack is a very powerful and flexible tool. It applies to a lot of use cases and that is one of the reasons it has so many configuration options. Webpack also evolved over the years but preserved backwards compatibility as much as possible to support the large ecosystem built around it.

Jetpack is an exploration of how using webpack could be made easier if the defaults, the CLI usage patterns and the configuration would be different.

I would be very interested in hearing your feedback. You might be new to JavaScript development, you tried jetpack and got stuck with something – I'd like to fix that. Or perhaps you're a seasoned webpacker in which case I _know_ you saw some specific aspect you probably didn't like, and I'd like to hear about that too.
