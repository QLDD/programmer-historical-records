### 1、Mac 下 electron 之 Not allowed to load local resource



```js
let newWindow = new BrowserWindow ({
            'minWidth': 700,
            'minHeight': 700,
            'width': 1000,
            'height': 800,        
            'fullscreenable': true,
            'show': false,                
            'backgroundColor': '#fbfbfb',
            webPreferences: {
                webSecurity: false,
                allowRunningInsecureContent: true
            }
        });                    

        let urlTitle = process.argv[0].substring(0, process.argv[0].indexOf('node_modules'));
        let urlLocal = `file://${urlTitle}dist/electron/dist/index.html`;

        const mindMapUrl = process.env.NODE_ENV === 'development' 
            ? platform == 'darwin' ? urlLocal : `file:///dist/electron/dist/index.html`
            : `file://${__dirname}/dist/index.html`;                             

        newWindow.loadURL(mindMapUrl);
```

- 关键点

``` js
webPreferences: {
    webSecurity: false,
        allowRunningInsecureContent: true
}
```

- 详情：https://electronjs.org/docs/api/browser-window

