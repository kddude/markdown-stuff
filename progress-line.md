# Progress-Line

![Progress-Line](http://i.imgur.com/ynco5f5.png) ![Sponsor Step](http://i.imgur.com/DugH5iM.png)

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
	       },
				 {
           title: 'Sponsor',
           associatedStates: ['Sponsor'],
           type: 'icon-svg',
           svgHoverText: 'Grant Runner submitted to Grants.gov',
           svgCode: '*INSERT SVG CODE HERE*',
           iconTitleTextReached: 'sponsor - checked',
           iconTitleTextUnreached: 'sponsor - unchecked'
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
* `iconTitleTextReached`
* `iconTitleTextUnreached`
* `text`**
* `iconName`**
* `svgCode`**
* `svgHoverText`**

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
	       },
				 {
           title: 'Sponsor',
           associatedStates: ['Sponsor'],
           type: 'icon-svg',
           svgHoverText: 'Grant Runner submitted to Grants.gov',
           svgCode: '*INSERT SVG CODE HERE*',
           iconTitleTextReached: 'sponsor - checked',
           iconTitleTextUnreached: 'sponsor - unchecked'
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
