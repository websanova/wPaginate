# wPaginate.js

A jQuery pagination plugin for simply setting up pagination on the fly.  The plugin allows you to set how many pages are displayed at a time on a sliding scale and also has ajax support out of the box.

* [View the wPaginate demo](http://wpaginate.websanova.com)
* [Download the lastest version of wPaginate](https://github.com/websanova/wPaginate/tags)


## Related Plugins

* [wForm](http://wform.websanova.com) - A combination of plugins for elegant looking forms.


## Settings

Available options with notes, the values here are the defaults.

```javascript
$.fn.wPaginate.defaultSettings = {
    theme           : 'black',      // theme for plugin to use
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


## Examples

Include the following files:

```js
<script type="text/javascript" src="./wPaginate.js"></script>
<link rel="Stylesheet" type="text/css" href="./wPaginate.css" />
```

### init

Init with static url:

```js
$("#elem").wPaginate({
    theme: 'green',
    total: 123,
    index: 40,
    limit: 20,
    url: '/results/page'
});
```

Init with dynamic url:

```js
$("#elem").wPaginate({
    theme: 'red',
    total: 123,
    index: 40,
    limit: 20,
    url: function(i){ return '/some/' + i + '/path'; }
});
```

### ajax

```js
$("#elem").wPaginate({
    theme: 'red',
    total: 123,
    index: 40,
    limit: 20,
    url: function(i){ /* load page here */ },
    ajax: true
});
```

### themes

A few default styling themes are provided in the `wPaginate.css` file, however you can be easily add your own by following the styling indicated there which should look something similar to the sampel below:

```css
._wPaginate_black ._wPaginate_link{border-color:#000; color:#000;}
._wPaginate_black ._wPaginate_link:hover,
._wPaginate_black ._wPaginate_link_active{border-color:#FF0000; color:#FF0000;}
```

### destroy

Remove pagination on the speicified element.

```html
$('#elem').wPaginate('destroy');
```


## Resources

* [More jQuery plugins by Websanova](http://websanova.com/plugins)
* [jQuery Plugin Development Boilerplate](http://www.websanova.com/tutorials/jquery/jquery-plugin-development-boilerplate)
* [The Ultimate Guide to Writing jQuery Plugins](http://www.websanova.com/tutorials/jquery/the-ultimate-guide-to-writing-jquery-plugins)


## License

MIT licensed

Copyright (C) 2011-2012 Websanova http://www.websanova.com