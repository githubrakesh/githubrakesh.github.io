### App wide configuration settings:
```javascript
Ext.define('MyApp.util.Config', {
    singleton : true,
    
    constructor: function (conf) {
        this.initConfig(conf);
    },

    config : {
        baseUrl : 'something.com/foo.html'
    }
});
```

Usage:
```javascript
MyApp.util.Config.getBaseUrl();
```
