# List

![Card-List](http://i.imgur.com/NPYAHUf.png)
	
	<oris-card-list 
		list="items">
	</oris-card-list>
        
        
    items: 
    [
      {
        name: "For Check",
      },
      {
        name: "<p>Pending Fully Executed Agreement</p>",
      },
    ],
---

The progress-line directive accepts one input:

* `list`
	       
---
####list (array of objects)

The list input accepts an array of objects with the following property or more:

* `name`

The 'name' property will be displayed in the list section. This can be HTML, numbers, dates, or just plain strings.

Anything else is additional and may be passed in as desired. The minimum array you can pass in would look like this:

	[{name: 'hi'}]


#####passing in more advanced html

![example](http://i.imgur.com/iBj7RVK.png)

	htmlToPassIn = "<a href="#"> <code> For Check </code></a>'"
	
	items: 
    [
      {
        name: {{htmlToPassIn}},
      },
    ],
    
  
With this method, you may not pass in HTML that may compromise the security of the app. Angular will automatically filter out anything such as <html style="color: red;">, or any other attributes inside the html like that. This includes angular directives.
