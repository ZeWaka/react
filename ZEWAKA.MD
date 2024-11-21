# steps


## here

root directory:
```sh
yarn
yarn build-for-devtools
```

`cd packages\react-devtools-core`

run `yarn start:backend` and `yarn start:standalone`

`cd packages/react-devtools`

run `yarn start`


## byond

`tgui.html`

```diff
	<meta charset="utf-8">
+	<script src="http://localhost:8097"></script>

	<!-- Inlined metadata -->
	<meta id="tgui:windowId" content="[tgui:windowId]">
```

`webpack.config.js`

```diff
- const mode = argv.mode || 'production';
+ const mode = argv.mode || 'development';
```

```diff
    optimization: {
+     minimize: false,
      emitOnErrors: false,
    },
```

```diff
      new webpack.EnvironmentPlugin({
        NODE_ENV: env.NODE_ENV || mode,
-       WEBPACK_HMR_ENABLED: env.WEBPACK_HMR_ENABLED || argv.hot || false,
        DEV_SERVER_IP: env.DEV_SERVER_IP || null,
      }),
```
