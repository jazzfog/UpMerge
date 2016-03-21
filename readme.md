# UpMerge
*JavaScript Object Merge for Client or Server side*

## Usage

**Client side**

Include lib file to your HTML document

```html
<script src="../upmerge.js"></script>
```

Merge JavaScript objects

```javascript
<script type="text/javascript">

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

	var resultObj = upmerge.merge(obj1, obj2, options);

	console.log(resultObj);

</script>
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
