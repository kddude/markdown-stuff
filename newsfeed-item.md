# Newsfeed-item

A newsfeed item is a notification-like prefixed display for information.

![Newsfeed item](http://i.imgur.com/jeG3zwE.png)

```
<oris-newsfeed-item
	title="News item"
	date-time="2017-1-03 15:30:00"
	details="The details about the news item you recieved"
	urgency="danger">
</oris-newsfeed-item>
```

---

The container-box directive accepts 7 input:

* `title` (string)
* `date-time` (date)
* `details` (string)
* `urgency` (string)

** required

---
#### title (string)

The title of the newsfeed item to display next to the icon.

#### date-time (date)

The date of the item. This must be in a date format recognizable by MomentJS date library. It will be displayed in relative time to the current time (i.e. 7 days ago, 1 hour ago, 5 minutes ago, etc.)

#### details (string)

The details body of the newsfeed item.

#### urgency (string)

The urgency of the message. This will dictate the icon in the newsfeed item. You must choose from one of the following mappings:

`danger`: ![Red !](http://i.imgur.com/kQgbOQ2.png)

`warning`: ![Yellow !](http://i.imgur.com/IHfw2M9.png)

`success`: ![Green checkmark](http://i.imgur.com/7l4T47Z.png)

`info`: ![Blue i](http://i.imgur.com/pyjhm7z.png)
