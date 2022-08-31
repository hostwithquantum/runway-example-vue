

# Runway Example vue App

This is an example app demonstrating how to deploy a vue app
to [runway](https://runway.planetary-quantum.com/).

* clone this repo, and navigate into that directory
* `runway app create`
* `runway app deploy`
* `runway open`

You can then deploy changes by `git commit`ing them, and running `runway app
deploy` again.

This is a vue project created with `npm init vue@latest`. That initializes
a project that can be run locally, via `npm run dev`, but it doesn't set up
a production/deployment environment.

This example uses a node static file server to serve the vue build:
* `npm install --save http-server`
* `npm pkg set scripts.start='http-server --port $PORT --gzip true ./dist'`

There are other possibilities, including [running vue with server-side
rendering](https://vitejs.dev/guide/ssr.html). The important thing for
deployment on runway is:

* in `package.json`, `scripts.start` then starts the server
* the server must listen on the port given by the environment variable `PORT`

