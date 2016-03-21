# UpMerge
**JavaScript Object Merge for Client or Server side**

## Usage

**Client side**

Include lib file to your HTML document

```html
<script src="../upmerge.js"></script>
```

Merge JavaScript objects

```javascript
<script type="text/javascript">

	var options = {
			clone: true,
			deep: true,
			replaceOnly: false
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
