### Dynamically create Sencha Models from my server-side or How can we dynamically inject fields

* Use the ``` constructor ``` method of the Store class

```
Ext.define('App.store.MyStore', {
  extend: 'Ext.data.Store',
  
  constructor: function(){
      var me = this;
      me.callParent();

      Ext.Ajax.request({
        url: '../data?action=schema',
        success: function(response) {
          try{
            var resp = response.responseText;
            if(resp) {
              var data = Ext.JSON.decode(resp);

              var model = Ext.define("App.model.MyModel", {
                  extend: "Ext.data.Model",
                  fields: data.fields
              });

              me.model = model.$className;
            }
          }catch(e){
            console.error(e);
          }
        },
        failure: function(e){
          console.error(e);
        }
    });
  }
});
```
