# PolymerElements.LogBehavior
`PolymerElements.LogBehavior` wraps the [visionmedia/debug](https://github.com/visionmedia/debug) library to
 enable filterable logging per element and level.

 To enable logs `visionmedia/debug` requires localeStorage.debug to be set to your desired scope,
 e.g. `my-element:error`.
 For your convenience this can be done using an instance of the bundled &lt;locale-storage&gt; element, instead of
 setting the scope directly via your browser console.

 It is meant to be used in development as well as in production.
 
 See the component page for full documentation.

 Example usage:

```
    <dom-module id="my-element">
       <template>
         <locale-storage debug="my-element:*"></locale-storage>
       </template>
       <script>
          Polymer({

            is: 'my-element',

            behaviors: [
              PolymerElements.LogBehavior
            ],

            ready: function() {
              this._log.info('this is an info message');
              this._log.debug('this is a debug message');
              this._log.trace('this is a trace message');
              this._log.warn('this is a warn message');
              this._log.error('this is a error message');
            },
          });
       &lt;/script>
    </dom-module>
```     