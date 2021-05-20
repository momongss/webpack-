import ".확장자" 의 형식으로 js 파일 외의 파일(에셋)들을 불러올 수 있다.

현재 js 모듈이 어떤 에셋을 사용하고 있는 확실히 명시할 수 있어 모듈화에 도움이된다.

특히, 반드시 html 에 명시해야했던 css 파일을 js 파일에 명시할 수 있게된다.

rules 에 추가

## css

- npm i -D css-loader style-loader

---

    -- webpack.config.js --
    rules: [
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
        --------------------
        import './style.css';
    ]

## image

- npm i -D file-loader

---

    -- webpack.config.js --
    rules: [
        {
            test: /\.(png|jpe?g|gif)$/i,
            use: [
                {
                loader: "file-loader",
                },
            ],
        },
    ]

## fonts

- npm i -D file-loader

---

    -- webpack.config.js --
    rules: [
        {
            test: /\.(woff|woff2|eot|ttf|otf)$/i,
            use: [
                'file-loader',
            ],
        }
    ]

    --------------------

    -- .css --
    @font-face {
        font-family: 'MyFont';
        src: url('./my-font.woff2') format('woff2'),
            url('./my-font.woff') format('woff');
        font-weight: 600;
        font-style: normal;
    }

    .hello {
        font-family: 'MyFont';
    }

## xml, csv

- npm install --save-dev csv-loader xml-loader

---

    {
        test: /\.(csv|tsv)$/i,
        use: ['csv-loader'],
    },
    {
        test: /\.xml$/i,
        use: ['xml-loader'],
    },
    --------------------
    import Data from './data.xml';
    import Notes from './data.csv';

## parser of JSON modules

- npm install toml yamljs json5 --save-dev

---

    const toml = require('toml');
    const yaml = require('yamljs');
    const json5 = require('json5');
    -----------------
    {
        test: /\.toml$/i,
        type: 'json',
        parser: {
            parse: toml.parse,
        },
    },
    {
        test: /\.yaml$/i,
        type: 'json',
        parser: {
            parse: yaml.parse,
        },
    },
    {
        test: /\.json5$/i,
        type: 'json',
        parser: {
            parse: json5.parse,
        },
    },
    --------------------
    import toml from './data.toml';
    import yaml from './data.yaml';
    import json from './data.json5';
