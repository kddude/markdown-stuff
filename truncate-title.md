# Truncate-title

Truncate-title simply truncates the title after the character length provided.
After that, the remaining text will be replaced with "..."

```
{{"This string is 35 characters long" | | truncateTitle:20}}
```

The above code would produce the following:

`This string is 35 ch...` (concatenated to 20 characters minus the 3 "..." characters).
