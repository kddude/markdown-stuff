# Progress-Line

![Progress-Line](http://i.imgur.com/ynco5f5.png)
	
	<oris-progress-line
          current-state="Done"
          steps="item.progressLineData.data"
          condition="{{item.progressLineData.condition}}">
    </oris-progress-line>
    

	progressLineData {
		data: [
          {
            title: 'OSP',
            associatedStates: ['In OSP', 'Sent to OSP'],
            type: 'bar',
          },
          {
            title: 'GCA',
            associatedStates: ['In GCA', 'Sent to GCA'],
            type: 'bar'
          },
          {
            title: 'Done',
            associatedStates: ['Done'],
            type: 'icon',
            iconName: 'check'
          },
          {
            title: 'Budget #',
            associatedStates: ['Processed', 'Awarded'],
            type: 'text',
            text: '67-8134'
	       }
	     ],
	     condition: 'good'
	 }    
        
---

The progress-line directive accepts three inputs:

* `current-state`
* `steps`
* `condition` 	      
 
---
####current-state (string)

The current-state is whatever state the progress line will display at the time.
This must be set to one of the 'associatedStates' values in the steps array,
else it will throw an error and the progress-line will not show. See below
for `steps` info.


####steps (array of Step objects)

A 'Step' object consists of the following:

* `title `
* `associatedStates`
* `type `
* `text`**
* `iconName`**

** (situational)

######example steps:


		data: [
          {
            title: 'OSP',
            associatedStates: ['In OSP', 'Sent to OSP'],
            type: 'bar',
          },
          {
            title: 'GCA',
            associatedStates: ['In GCA', 'Sent to GCA'],
            type: 'bar'
          },
          {
            title: 'Done',
            associatedStates: ['Done'],
            type: 'icon',
            iconName: 'check'
          },
          {
            title: 'Budget #',
            associatedStates: ['Processed', 'Awarded'],
            type: 'text',
            text: '67-8134'
	       }
	     ],


#####title:
*(string)* the title of the step that will show above it.

#####assocaitedStates: 
an *array of strings* of the names of the states that will trigger the progress-line to show that step as 'current'.

`associatedStates: ['In OSP', 'Sent to OSP']`
    

#####type:
*string*

type can be one of the following: **bar, icon, text**

###### **bar**: the standard progress line bar background

	{
       title: 'OSP',
       associatedStates: ['In OSP', 'Sent to OSP'],
       type: 'bar'
   	}
   	
###### icon: a font-awesome icon
The `iconName` (string) is required, and the icon you choose must be from the [FontAwesome Library](https://fortawesome.github.io/Font-Awesome/icons/).


	{
       title: 'Done',
       associatedStates: ['Done'],
       type: 'icon',
       iconName: 'check'
   	}
   	
###### text: any string
`text` is required, and is a string.

	{
       title: 'Budget #',
       associatedStates: ['Processed', 'Awarded'],
       type: 'text',
       text: '67-8134'
   	}
   	

###condition

A flag that will tell the progress-line to display whatever current step it is
at with either neutral, good, or bad. 

	condition: 'good' // good, bad, or neutral

`good` is green, `bad` is red, and `neutral` is grey.

example of `bad`:

![](http://i.imgur.com/bs6K5Ka.png)     



---
---
---

# Status-block

![Status Block](http://i.imgur.com/4zAXmVK.png)
	
	<oris-status-block
       status-text="Routing"
       status-icon="file-text-o"
       status-color="green"
       status-date="{{item.statusActionDate | date}}"
       status-subtext="Due to OSP in 2 days">
     </oris-status-block>
            
---

The status block directive accepts 5 inputs:

* `status-text`
* `status-icon`
* `status-color`**	  
* `status-date`**
* `status-subtext`**

(** optional)
 
---
####status-text (string) - required

The text to show in big letters.


####status-icon (string) - required

A string of a [FontAwesome](https://fortawesome.github.io/Font-Awesome/icons/) icon name to show.

###status-color (string)

A string of the color you want the icon/title to show. There are 3 options:

* neutral (default, grey)
* green
* red

###status-date (string)

A date to show. Additionally, this can be a non-date string if you want.

###status-subtext (string)

Subtext to show below the date.







---








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






---






# Quote

![Card-Quote](http://i.imgur.com/VIbLFJV.png)
	
	<oris-card-quote
      quote="Placed on Hold."
      author="Kamran Salehi"
      date="08/17/2015">
    </oris-card-quote>  st>
                          ],
---

The progress-line directive accepts three inputs:

* `quote`
* `author`**
* `date`** 
	      
** (optional)	      
 
---
####quote (string)

The quote input is a string of the quote you want displayed. There is currently no limit on its size,
however, it is recomended that if it is large you make the card size medium or larger.


####author (string) - optional

The optional author input is a string of the name of the author of the quote, or any text you wish to display in the author section.  	
 
###date (string) - optional

The optional date input is a string of you wish to display with the quote. **This must be some kind of date string that Angular can accept. **   

