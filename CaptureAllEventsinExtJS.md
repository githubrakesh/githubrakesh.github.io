#### Listen to all events fired by a specific component. There is actually a handy built-in static method to do this called [Ext.util.Observable.capture()](https://docs.sencha.com/extjs/6.5.3/classic/Ext.util.Observable.html).
 * Class  ```Ext.mixin.Observable``` in 5.x & 6.5.x
 * Class  ```Ext.util.Observable``` in 4.x

This logs the event name and all arguments:

```javascript

Ext.util.Observable.capture(myObj, function (evname) {
    console.log(evname, arguments);
});
```

Even better, if you're currently inspecting your component's main element in your browser's developer tools, you can do this:

```javascript
Ext.util.Observable.capture(Ext.getCmp($0.id), function (evname) {
    console.log(evname, arguments);
});
```
Where ```$0``` is the currently selected element. Should work fine in Chrome, Firefox, Opera, Safari.

If you don't want those logs to pollute your console anymore, simply call ``` releaseCapture``` on your object:

```javascript
Ext.util.Observable.releaseCapture(myObj);
```

This removes all captures on a given object so you don't have to reference your listener explicitly (which was likely an anonymous function 

#### The ```observe``` method which does something similar but allows you to listen to all events fired by  _all_ instances of a given class.
