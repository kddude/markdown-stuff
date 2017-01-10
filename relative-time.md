# Relative-time

Relative-time is a simple filter that formats date-time in a manner that displays
the time from the current date in a past or future tense. For example,

in 1 day, 1 day ago, in 3 months, 2 years ago.

The bindings are as follows:

```
future: 'in %s',
past:   '%s ago',
s:      'a few seconds',
m:      'a minute',
mm:     '%d minutes',
h:      'an hour',
hh:     '%d hours',
d:      'a day',
```

![Relative-Time](http://i.imgur.com/xZ6o8HB.png)

```
{{item.actionDate | relativeTime }}
```
