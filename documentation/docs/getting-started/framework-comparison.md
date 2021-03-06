# Framework comparison

Fusion.js is an open source web framework, originally created by Uber. It's comprised of a CLI, a webpack/babel transpilation pipeline, a Koa server, and a plugin-based isomorphic runtime architecture.

In addition to these core areas, the Fusion.js team provides several plugins for various things: from React and Redux to translations and CSRF protection. This makes Fusion.js a one-stop shop for full stack development, while at the same time making it easy to keep bundle size small by allowing developers to only include what they need.

Here is how Fusion.js compares to some popular frameworks and libraries:

### React

[React](https://reactjs.org/) is a popular and mature library developed by Facebook for implementing component-based UIs. Fusion.js can be used seamlessly with React: JSX, ES2017, hot module reloading, server-side rendering, etc. all work out of the box. In addition, the Fusion.js core is view-layer agnostic and can be used with different view libraries as well.

Through plugins, Fusion.js provides various extra features on top of vanilla React: it provides an easy way to do code splitting, it supports async server-side rendering, it allows plugins to automatically install providers when needed, etc.

#### create-react-app

[create-react-app](https://github.com/facebookincubator/create-react-app) is a CLI that scaffolds a React project, as well as configure Webpack, Babel, Eslint, Jest, etc. There are some things it doesn't support out of the box (most notably, server rendering and hot reloading of components), but it provides the ability to "eject", so you can use it as a boilerplate generator and customize the build workflow from there.

Fusion.js is similar to create-react-app in the sense that it provides a Webpack/Babel setup, but in addition to that, it provides higher level tools like server-side rendering, more powerful code splitting and fully integrated hot reloading. Fusion.js also provides a modern HTTP server API (through [Koa](http://koajs.com/)) and a universal code environment.

Because Fusion.js provides the compilation pipeline, as well as both the server and browser environments, it has the potential to automatically apply several optimizations that would otherwise need to be done manually for every application.

### Express

[Express](https://expressjs.com/) is the most popular HTTP server framework for Node.js. While it is agnostic of rendering libraries (being compatible with libraries such as pug or handlebars), it's generally not as trivial to integrate to modern React tooling (e.g. HMR) unless you adopt a more opinionated framework on top of Express.

Both Express and Fusion.js can be used as a Node.js server and both can be composed via middlewares. The major difference is that Fusion.js uses Koa.js middlewares. Koa uses a more modern async/await based middleware architecture, which gives a better stack trace/debugging experience and is easier to test.

### Next.js

[Next.js](https://github.com/zeit/next.js/) is a framework developed by Zeit.co designed for building server-rendered React applications.

The main difference is that Next.js focuses on React development and doesn't provide facilities for developing full-on backends, whereas Fusion.js is a full stack framework, which supports backend development through [Koa](http://koajs.com/) middleware, and plugins for tools like GraphQL. In addition, Fusion.js provides facilities such as dependency injection and static typing to improve maintainability of complex projects.

Both Next.js and Fusion.js can be used with a variety of 3rd party libraries, but in the interest of avoiding analysis paralysis, the Fusion.js team also provides a curated set of plugins that we consider important for production-quality applications and that can integrate into a base app in a way that is performant and boilerplate-free.

### Electrode.io

[Electrode](http://www.electrode.io/) is a framework developed by Walmart Labs designed for building server-rendered React applications. It's very similar in scope to Fusion.js.

Instead of providing a single monolithic scaffold, Fusion.js architecture encapsulates complex integrations on a per-library basis, allowing scaffolds to be as simple or as complex as you need. For example, installing support for atomic CSS takes a single line of code, and different styling strategies can be packaged and shared across projects easily.
