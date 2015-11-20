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

