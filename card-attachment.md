# Card-attachment

This directive essentially wraps a stylized block around any content you want to use as an "attachment" to some card or newsfeed item.

![Card Attachment](http://i.imgur.com/K9XpUGs.png)

```
<oris-card-attachment
	link="{{item.attachmentLink}}"
	link-title="{{item.attachment.parsedTitle}}"
	analytics="item.attachment.analytics">

	*** any content ***

</oris-card-attachment>
```

---

The status block directive accepts 3 inputs:

* `link`**
* `link-title`**
* `analytics`**

(** optional)

---
#### link (string)

The link the card will go to when you click anywhere on its body


#### link-title (string)

The title you want the link to show when you hover over it.

#### analytics

Special analytics parameter for MR usage.
