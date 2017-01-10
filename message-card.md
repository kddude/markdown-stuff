# Message-card

A simple message card that displays content in an email-like message format.

![Message card](http://i.imgur.com/44B4h5P.png)

```
<oris-message-card
	message-title="Regarding Your Award"
	message-subtitle="Sponsor Award # 1234"
	message-subject="Comments from Supervisor"
	message-body="Some body text goes here"
	message-icon="comment">
</oris-message-card>
```

---

The container-box directive accepts 7 input:

* `message-title` (string)
* `message-subtitle` (string)
* `message-subject` (string)
* `message-body` (string)
* `message-icon` (string)

** required

---
#### message-title (string)

The title of the message to display.

#### message-subtitle (string)

The subtitle of the message to display. (small text on the same line as title)

#### message-subject (string)

The subject of the message. This goes on the second line next to the icon.

#### message-body (string)

The body of the message.

#### message-icon (string)

A Font-Awesome icon name to use next to the subject. The directive automatically adds the `fa-` prefix to the icon name, so you just type the plain name of the icon to use. Library is linked below:

http://fontawesome.io/cheatsheet/
