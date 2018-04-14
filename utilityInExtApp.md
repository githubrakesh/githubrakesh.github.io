### App wide configuration settings:
```javascript
Ext.define('MyApp.util.Config', {
    singleton : true,

    config : {
        baseUrl : 'something.com/foo.html'
    }
});
```

Usage:
```javascript
MyApp.util.Config.getBaseUrl();
```
