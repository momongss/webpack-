## Single Entry (Shorthand) Syntax

    -- webpack.config.js --
    ---- Shorthand ----

    module.exports = {
        entry: './path/file.js',
    }

    -- webpack.config.js --
    ---- full ----

    module.exports = {
        entry: {
            main: './path/to/my/entry/file.js',
        },
    };

**multi-main entry**

    module.exports = {
        entry: {
            main: ['./src/file_1.js', './src/file_2.js'],
        },
        output: {
            filename: 'bundle.js',
        },
    };

2개 이상 entry points => 1개 output <br>
-> 언제 필요한 걸까? <br>

- 한 페이지에서 2개의 독립된 흐름이 필요할 때.
- 거의 모든 경우 완전히 독립된 흐름은 없지만, 연결이 많이 느슨하다면 이렇게 만들 수도 있을 듯.
