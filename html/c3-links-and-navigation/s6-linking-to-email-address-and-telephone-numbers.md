To create links that open in the user's email program to let them send a new message, use the mailto: scheme:

```html
<a href="mailto:nowhere@mozilla.org">Send email to nowhere
</a>
```
For details about mailto: URLs, such as including a subject or body, see Email links or RFC 6068.

Linking to telephone numbers

```html
<a href="tel:+49.157.0156">+49 157 0156</a>
<a href="tel:+1(555)5309">(555) 5309</a>
```

`tel`: link behavior varies with device capabilities:

* Cellular devices autodial the number.
* Most operating systems have programs that can make calls, like Skype on Windows or FaceTime on MacOS.
* Other behaviors include saving the number to contacts, or sending the number to another device (a new feature in chrome that dials the number on your phone if your devices are synced).