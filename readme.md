# UpMerge
*JavaScript Object Merge for Client or Server side*

## Installation

Server side, via `npm`:

`npm install upmerge`

Client side:

Download file `build/upmerge.js`, put it under your `public` directory and include it in your HTML

```html
<script src="upmerge.js"></script>
```

Install via bower will be available later

## Usage

Consider you have two objects

```JavaScript
	var obj1 = {
		a: 'Hi',
		b: 'World',
		c: {
			a: 'Alpha',
			b: 'Beta'
		}
	};

	var obj2 = {
		a: 'Hello',
		c: {
			g: 'Gamma',
			d: 'Delta'
		},
		d: 'Wow'
	};
```

You merge them with function `merge()` using set of options

```
// The values shown here are defaults so if you do not need to change 
// anything - you can skip `options` argument, it is optional
var options = {
	// Clone obj1 so it will not be changed during merge
	clone: true,
	// Recursive `deep` merge - all object levels will be merged in opposite to first-level
	deep: true,
	 // Only replace existing key/values in original object, return `null` if obj2 contains key
	replaceOnly: false with does not exist in obj1
};
```

Now, how you do it on client or server

**Client side**

```javascript
<script type="text/javascript">
	var resultObj = upmerge.merge(obj1, obj2, options);
	console.log(resultObj);
</script>
```

**Server side**

```javascript
var um = require('upmerge');
//... declare `obj1`, `obj2` and `options` here.
var resultObj = upmerge.merge(obj1, obj2, options);
console.log(resultObj);
```

The result will be:

```javascript
{
	a: 'Hello',
	b: 'World',
	c: {
		a: 'Alpha',
		b: 'Beta',
		g: 'Gamma',
		d: 'Delta'
	},
	d: 'Wow'
}
```

## Testing library

Go to directory `Tests` and run `bower install` it will install testing framework `qunit` then just open `Tests/index.html` in your browser.

Little bit more information about test cases structure you will find in `cases.js`.
