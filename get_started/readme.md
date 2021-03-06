
Install the webpack and commandline
*   npm i webpack webpack-cli -D
add script in package.json
*   "build": "webpack --mode production --config script/webpack.config.prod.js"
build up a webpack.config.prod.js file
run build
*   npm run build

install html webpack plugin
*   npm i --save-dev html-webpack-plugin
*   add in webpack.config.prod.js
```
    plugins: [
            new HtmlWebpackPlugin()
        ]
```

css loader
*   npm i --save-dev css-loader
*   npm i --save-dev style-loader

remain css files in dist
*  mini-css-extract-plugin
    *  npm i --save-dev mini-css-extract-plugin
    *    add const MiniCssExtractPlugin = require('mini-css-extract-plugin');
```
    new MiniCssExtractPlugin({
                  // Options similar to the same options in webpackOptions.output
                  // both options are optional
                  filename: '[name].[chunkHash:6]css',
              })
```
*   change 'style-loader' to MiniCssExtractPlugin.loader



local server
*   npm i --save-dev webpack-dev-server
*   add into package.json  "dev": "webpack-dev-server --mode development --config script/webpack.config.prod.js"
*   add into webpack.config.prod.js
```
 devServer:{
        port:3000,
        open: true
    }
```
less loader
*   npm i less-loader less --save-dev
*   add rules in webpack.config.prod.js



post cssprefixer
*   npm i postcss-loader autoprefixer -D
*   add  'postcss-loader', after css-loader
*   add into postcss.config.js
```
module.exports = {
    plugins: [
        require('autoprefixer')
    ]
}
```
add into package.json
```
  "browserslist": [
    "cover 99.5%"
  ]
```

resource loader
*   npm i file-loader -D
*   edit in webpack.config.prod.js
```
 {
                test: /\.(png|jpe?g|gif)$/i,
                loader: 'file-loader',
                options: {
                    name: 'static/images/[name].[ext]',
                    publicPath: "/"
                },
            },
```
*   edit in package.json
```
      "browserslist": [
        "cover 99.5%"
      ]
```


url loader like file loader, compress the file additionally
*   npm i url-loader --save-dev
*   edit in webpack.config.prod.js

copy directory  used to image in html file (02.jpg)
* npm i copy-webpack-plugin --save-dev
*

install babel
*   npm install -D babel-loader @babel/core @babel/preset-env
*   add into webpack.config.prod.js rules




if want to user different webpack config, just change the script


create react app
npx create-react-app my-app(this is the directory name)
