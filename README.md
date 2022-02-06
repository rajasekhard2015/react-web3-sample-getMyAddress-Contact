# react-web3-sample-getMyAddress-Contact

web3.0 react native support
Create react application : npx create-react-app contacts -- yarn add web3 --after adding getting issues realted web3 to solve them using --yarn add --dev react-app-rewired crypto-browserify stream-browserify assert stream-http https-browserify os-browserify url buffer

step1: create confi-overrides.js file
--const webpack = require('webpack');

--module.exports = function override(config) { const fallback = config.resolve.fallback || {}; Object.assign(fallback, { "crypto": require.resolve("crypto-browserify"), "stream": require.resolve("stream-browserify"), "assert": require.resolve("assert"), "http": require.resolve("stream-http"), "https": require.resolve("https-browserify"), "os": require.resolve("os-browserify"), "url": require.resolve("url") }) config.resolve.fallback = fallback; config.plugins = (config.plugins || []).concat([ new webpack.ProvidePlugin({ process: 'process/browser', Buffer: ['buffer', 'Buffer'] }) ]) config.ignoreWarnings = [/Failed to parse source map/]; return config; }

After that you can modifey the scripts in package.json
--"scripts": { "start": "react-app-rewired start", "build": "react-app-rewired build", "test": "react-app-rewired test", "eject": "react-scripts eject" }
