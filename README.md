# node-data-transform


First we need some data.

```javascript
var data = {
	posts : [
		{
			title : "title1",
			description: "description1",
			blog: "This is a blog.",
			date: "11/4/2013",
			extra : {
				link : "http://goo.cm"
			},
			list1:[],
			list2:[
				{
					item: "thing"
				}
			]
		}	
	]
};
```

The map defines how the output will be structured and which operations to run.

```javascript
var map = {
	list : 'posts',
	item: {
		name: "title",
		info: "description",
		text: "blog",
		date: "date",
		link: "extra.link",
		item: "list1.0.name"
	},
	operate: [
		{run: "Date.parse", on: "date"}
	]
};
```
You can read this as follows: 
- Get the array of objects in "posts".
- Map the name to title, info to description etc.
- Run Data.parse on the date value

The expected output.
```javascript
[{
	title : "title1",
	description: "description1",
	blog: "This is a blog.",
	date: "11/4/2013",
	extra : {
		link : "http://goo.cm"
	},
	list1:[],
	list2:[
		{
			item: "thing"
		}
	]
}] 
```

Enjoy!

## Credits

  - [Michael Bosworth](http://github.com/bozzltron)

## License

(The MIT License)

Copyright (c) 2014 Michael Bosworth

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.