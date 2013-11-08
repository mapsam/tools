Web Trix
========

##clearfix

I mostly use this when I'm ensuring the *footer* of a site gets pushed beneath all of my content that is split into two floating div elements. Does the trick and works from IE6 and beyond.

**CSS**

```CSS
.cf:before,
.cf:after {
	content:" ";
	display:table;
}
.cf:after {
	clear:both;
}
.cf {
	*zoom:1;
}
```
**HTML**

```HTML
<div class="cf"></div>
```

##target="_blank" everywhere

Single-line, jQuery script to convert all links on the page that navigate outside of the current website to create new tabs. This prevents people from accidentally closing a site by adding the `target='_blank'` attribute.

```JS
$('a[href^="http://"], a[href^="https://"]').not('a[href*="your_domain"]').attr('target', '_blank');
```

Currently only finds `<a href="">` tags with "http" and "https" that do NOT include the root directory name or domain name specified.