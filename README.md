# serverless-offline-alpha-webpack-bug

## Instructions

```
npm install
npm start
```

or

```
yarn
yarn start
```

Then visit [http://localhost:3000](http://localhost:3000), it should trigger the error:

```
serverless-offline-alpha-webpack-bug (master) $ npm start

> @ start /Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug
> serverless offline

Serverless: Bundling with Webpack...
Time: 317ms
Built at: 08/19/2019 1:39:03 PM
       Asset      Size  Chunks             Chunk Names
src/hello.js  1.07 KiB       0  [emitted]  src/hello
Entrypoint src/hello = src/hello.js
[0] ./src/hello.js 83 bytes {0} [built]

WARNING in configuration
The 'mode' option has not been set, webpack will fallback to 'production' for this value. Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/configuration/mode/
Serverless: Watching for changes...
offline: Starting Offline: prod/us-east-1.
offline:
offline: [HTTP] server ready: http://localhost:3000 🚀
offline:
offline: OpenAPI/Swagger documentation:
offline: [GET] http://localhost:3000/documentation
offline:
offline: Enter "rp" to replay the last request
offline:
offline: [ANY] http://localhost:3000/

offline: ANY / (λ: hello)
/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/src/hello.js:1
export const main = async (event, context) => ({ statusCode: 200, body: 'hello' })
^^^^^^

SyntaxError: Unexpected token export
    at Module._compile (internal/modules/cjs/loader.js:703:23)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:770:10)
    at Module.load (internal/modules/cjs/loader.js:628:32)
    at Function.Module._load (internal/modules/cjs/loader.js:555:12)
    at Module.require (internal/modules/cjs/loader.js:666:19)
    at require (internal/modules/cjs/helpers.js:16:16)
    at InProcessRunner.run (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/serverless-offline/src/handler-runner/InProcessRunner.js:19:21)
    at HandlerRunner.run (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/serverless-offline/src/handler-runner/HandlerRunner.js:114:25)
    at LambdaFunction.runHandler (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/serverless-offline/src/LambdaFunction.js:145:36)
    at hapiHandler (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/serverless-offline/src/ApiGateway.js:868:39)
    at module.exports.internals.Manager.execute (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/toolkit.js:41:33)
    at Object.internals.handler (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/handler.js:46:48)
    at exports.execute (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/handler.js:31:36)
    at Request._lifecycle (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/request.js:312:68)
    at processTicksAndRejections (internal/process/task_queues.js:89:5)
    at Request._execute (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/request.js:221:9)
offline: Failure: Uncaught error in 'hello' handler.
Error: Uncaught error in 'hello' handler.
    at LambdaFunction.runHandler (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/serverless-offline/src/LambdaFunction.js:150:13)
    at hapiHandler (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/serverless-offline/src/ApiGateway.js:868:39)
    at module.exports.internals.Manager.execute (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/toolkit.js:41:33)
    at Object.internals.handler (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/handler.js:46:48)
    at exports.execute (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/handler.js:31:36)
    at Request._lifecycle (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/request.js:312:68)
    at processTicksAndRejections (internal/process/task_queues.js:89:5)
    at Request._execute (/Users/verekia/Local/Code/serverless-offline-alpha-webpack-bug/node_modules/@hapi/hapi/lib/request.js:221:9)
```

Then, in `package.json`, replace `"serverless-offline": "6.0.0-alpha.13",` by `"serverless-offline": "5.10.1",`.

```
npm start
```

or

```
yarn start
```

Then visit [http://localhost:3000](http://localhost:3000). It works as expected.
