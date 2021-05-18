프로덕션 시에는 사용하지 말아야할 개발 전용 설정들이다. 문서에 나온 기능은 크게 2가지이다.

- 콜스택 보기
- 빌드 자동화

## Using source maps (콜스택 보기)

    -- webpack.config.js --

    module.exports = {
        devtool: 'inline-source-map',
    }

설정끝 이제 콜스택을 볼 수 있다.

## Using Watch Mode (빌드 자동화1)

    -- package.json --

    "scripts": {
        "watch": "webpack --watch",
        "build": "webpack"
    },

이제 npm run watch 로 매번 빌드를 해줄 필요가 없어진다. but, 브라우저 새로고침은 해줘야 한다.

## Using webpack-dev-server

- npm install --save-dev webpack-dev-server

---

    -- webpack.config.js --
    devServer: {
        contentBase: './dist',
    },

    -- package.json --
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "watch": "webpack --watch",
        "start": "webpack serve --open",
        "build": "webpack"
    },

npm start 로 실행한다. 이제 새로고침도 할 필요가 없다. (근데 왜 딴 애들은 npm run --- 인데 예만 npm --- 이지.)

## Using webpack-dev-middleware

webpack-dev-server 에 다른 기능을 추가할 수 있는 버전이다.
아래는 node 의 express 라이브러리와 연동해 자동으로 서버를 구축할 수 있는 예시이다.

(궁금증 : dev server와 그냥 server 차이가 뭐지?)

- npm install --save-dev express webpack-dev-middleware

---

    -- webpack.config.js --

    output: {
        filename: '[name].bundle.js',
        path: path.resolve(__dirname, 'dist'),
        clean: true,
        publicPath: '/',
    },

    -- server.js --
    const express = require('express');
    const webpack = require('webpack');
    const webpackDevMiddleware = require('webpack-dev-middleware');

    const app = express();
    const config = require('./webpack.config.js');
    const compiler = webpack(config);

    // Tell express to use the webpack-dev-middleware and use the webpack.config.js
    // configuration file as a base.
    app.use(
    webpackDevMiddleware(compiler, {
        publicPath: config.output.publicPath,
    })
    );

    // Serve the files on port 3000.
    app.listen(3000, function () {
    console.log('Example app listening on port 3000!\n');
    });

    -- package.json --

    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "watch": "webpack --watch",
        "start": "webpack serve --open",
        "server": "node server.js",
        "build": "webpack"
    },

백엔드까지 한번에..??
