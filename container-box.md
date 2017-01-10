# Container-box

A wrapper that includes a show more button and empty behavior used to wrap any number of recurring items you wish to show. For example, show 3 tweets at a time, click the "show more" button, and show X more.

![Container Box showing 3 items](http://i.imgur.com/m5aj6dL.png)

```
<oris-container-box
	show-more='clickShowMoreButton()'
	base-amount="newsfeed.baseAmount"
	add-amount="newsfeed.addAmount"
	expand-text="{{newsfeed.moreToShow ? 'SHOW MORE' : 'You\'ve reached the end of your newsfeed!'}}"
	more-to-show="newsfeed.moreToShow"
	is-loaded="newsfeed.newsDataLoaded"
	is-empty="newsfeed.isEmpty"
	empty-text="No items to show.">

	*** content ***

</oris-container-box>
```

---

The container-box directive accepts 7 input:

* `show-more` (function) **
* `base-amount` (number) **
* `add-amount` (number) **
* `expand-text` (string) **
* `more-to-show` (bool) **
* `is-loaded` (bool) **
* `is-empty` (bool) **
* `empty-text` (string)

** required

---
#### show-more (function)

The function to call when you click the 'show more' button. This can do anything you want it to. We usually use it to increase the our limit on child items showing in the container.

#### base-amount (number)

The starting limit of things to show in the container.

#### add-amount (number)

The amount to add to the limit when the "show more" button is clicked.

#### expand-text (string)

The text to show for the "show more" button at the bottom of the container. You can utilize angular conditions to show different text depending on the limit/amount of child data showing as seen in the example.

#### is-loaded (bool)

A boolean representing whether or not the content you wish to display has fully loaded or not yet. Useful for hiding content that isn't loaded so things display smoothly.

#### is-empty (bool)

A boolean representing whether or not there is any child content inside the container box. If empty, it will show default empty text. This must be false for most functionality to work.

#### empty-text (string)

The text to show when the container-box is empty.

## Important usage note:

In order for this directive to properly control and limit the number of items showing within it, you'll have to have some sort of `limit` variable in your `show-more` function that will be the master limit number. You will then need to reference this number utilizing the angular `ng-repeat | limitTo` filter on whatever you want to limit.

example:

js:
```
var clickShowMoreButton = function(limitNumber) {
	limitNumber += newsfeed.addAmount
}
```

html:
```
<p ng-repeat="i in newsfeed.paragraphs | limitTo : newsfeed.limitNumber">
</p>
```
