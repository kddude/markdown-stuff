# Status-block

![Status Block](http://i.imgur.com/HXuHTp7.png)
	
	<oris-status-block
       status-text="Routing"
       status-icon="['file-o']"
       status-icon-text="eGC1"
       status-icon-title="Hover Title"
       status-color="green"
       status-date="{{item.statusActionDate | date}}"
       status-subtext="Due to OSP in 2 days">
     </oris-status-block>
            
---

The status block directive accepts 7 inputs:

* `status-text`
* `status-icon`
* `status-icon-text`**
* `status-icon-title`**
* `status-color`**	  
* `status-date`**
* `status-subtext`**

(** optional)
 
---
####status-text (string) - required

The text to show in big letters.


####status-icon (array of strings) - required

An array of 1-2 strings of a [FontAwesome](https://fortawesome.github.io/Font-Awesome/icons/) icon name to show.

If you put more than 1 icon in the array, they will stack on top of each other.

####status-icon-text (string)

The text to overlay on top of the 1st icon provided in `status-icon`. If you have more than one `status-icon`, the first one will be used

####status-icon-title (string)

The title that will display when you hover over the icons. the `title` attribute in html.

####status-color (string)

A string of the color you want the icon/title to show. There are 3 options:

* neutral (default, grey)
* green
* red

####status-date (string)

A date to show. Additionally, this can be a non-date string if you want.

####status-subtext (string)

Subtext to show below the date.
