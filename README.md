BEM CSS loader
==============

The aim of this loader and plugin is to require needed css files from BEM project into Webpack one.
It's necessary to set up plugin:

```js
    // -----> in webpack.config.js
    var loader = require('bem-css-loader');
    var CollectBemAssetsPlugin = loader.CollectBemAssetsPlugin;

    module.exports = {
        // ...

        plugins: [
            new CollectBemAssetsPlugin({
                setData: loader.setData, // pass setData callback into plugin
                tech: 'css', // or maybe post.css
                // where to search css
                levels: [
                    './bem-project/common.blocks'),
                ]
            }),
        ]
    };
```

And use loader:

```js

    // -----> somewhere in code
    require('bem-css-loader!button.css'); // this file have to exist, also a name of the file is the name of BEM-block

    // ... Webpack should handle everything else
```