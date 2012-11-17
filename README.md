# wPaginate.js

A simple, lightweight and flexible jQuery pagination plugin with ajax support. [Check out the live demo](http://www.websanova.com/plugins/pagination).


## Settings

Available options with notes, the values here are the defaults.

```javascript
$.fn.wPaginate.defaultSettings = {
    theme           : 'default',    // theme for plugin to use
    first           : '<<',         // html for first page link (null for no link)
    prev            : '<',          // html for prev page link (null for no link)
    next            : '>',          // html for next page link (null for no link)
    last            : '>>',         // html for last page link (null for no link)
    spread          : 5,            // number of links to display on each side (total 11)
    total           : 400,          // total number of results
    index           : 0,            // current index, based on limit (0, 20, 40, etc)
    limit           : 20,           // increment for index
    url             : '#',          // url for pagination (also accepts function ex: function(i){ return '/path/' + i*this.settings.limit; })
    ajax            : false         // if ajax is set to true url will execute as a callback
};
```

Retrieve settings, if more than one it will return an array otherwise just the value.

```javascript
console.log($('#elem').wPaginate('total'));            // "400"
console.log($('.elem').wPaginate('total'));            // ["400", "200"]
```


## Methods

```html
$('#elem').wPaginate('destroy');
```


## Examples

Init with some values:

```javascript
$("body").wPaginate({
    theme: 'green',
    total: 123,
    index: 40,
    limit: 20,
    url: '/results/page'
});
```

Init with dynamic url:

```javascript
$("body").wPaginate({
    theme: 'red',
    total: 123,
    index: 40,
    limit: 20,
    url: function(i){ return '/some/' + i + '/path'; }
});
```

Enable ajax with url as callback

```javascript
$("body").wPaginate({
    theme: 'red',
    total: 123,
    index: 40,
    limit: 20,
    url: function(i){ /* load page here */ },
    ajax: true
});
```


## Themes

A few default styling themes are provided in the `wPaginate.css` file, however you can be easily add your own by following the styling indicated there which should look something similar to the sampel below:

```css
._wPaginate_black ._wPaginate_link{border-color:#000; color:#000;}
._wPaginate_black ._wPaginate_link:hover,
._wPaginate_black ._wPaginate_link_active{border-color:#FF0000; color:#FF0000;}
```


## Resources

* [jQuery Plugin Development Boilerplate](http://www.websanova.com/tutorials/jquery/jquery-plugin-development-boilerplate)
* [The Ultimate Guide to Writing jQuery Plugins](http://www.websanova.com/tutorials/jquery/the-ultimate-guide-to-writing-jquery-plugins)


## License

MIT licensed

Copyright (C) 2011-2012 Websanova http://www.websanova.com