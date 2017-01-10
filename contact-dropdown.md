# Contact-dropdown

A dropdown section used for contact information.

![Contact Dropdown (Pulled Up)](http://i.imgur.com/uoI4by5.png)


![Contact Dropdown (Expanded)](http://i.imgur.com/iDnSvy3.png)


```
<oris-contact-block
	name="Joe Smith"
	title="Contact Joe Smith"
	contact-info="contactInfoJsonItem (see below)"
	additional-info="additionalInfo (see below)">
</oris-contact-block>
```

---

The contact dropdown directive accepts 4 input:

* `name` (string)
* `title` (string)
* `contact-info` (object)
* `additional-info` (array)

** required

---
#### name (string)

The name of the contact to display

#### title (string)

The title to display on the header of the dropdown, i.e. "Contact Joe Smith"

#### contact-info (object)

The contact-info object can take any type of information want to show.
As long as your information has some `data`, and a `label` then it will show
anything you enter in.

The `link` field will tell the directive what type of link you are providing.
It will refer to the `url` field if you want a basic url, or it will
prefix your phone numbers or email addresses with the respective link types as follows:

- `mail`: "mailto:"
- `phone`: "tel:"

If there is no `link` item, the data will just be printed in plaintext with no url.

Sample contact-info object:

```
{
	"email": {
		data: ['email1@gmail.com', 'email2@gmail.com'],
		label: "Email",
		link: "mail" (optional)
	},
	"phone": {
		data: ['555-1111', '555-2222'],
		label: "Phone",
		link: "phone" (optional)
	},
	"department": {
		data: ['Office of Research'],
		label: "Department",
		link: "url",
		url: "http://uw.edu"
	}
}
```

#### additional-info (array)

The additional-info field can display any subheader/data you want within the contact
dropdown. It is similar to the contact-info object except it has no pre-defined
data types or headers.

- The `title` item in the object is the header displayed for that section. For example,
in the contact-info field the title is the `name` value. Here, it is anything you want.

- The `data` item must contain two things: `content` (whatever data to show), and
`label` (left label for the content). It can contain any amount of content/label
combinations.

Sample additional-info objects:

```
[
	{
		title: 'Personal Information',
		data: [
			{
				content: '25',
				label: 'Age'
			},
			{
				content: '123456789',
				label: 'ID #'
			}
		]
	},
	{
		title: 'Other Information',
		data: [
			{
				content: '123',
				label: 'Info #'
			}
		]
	},
]
```
