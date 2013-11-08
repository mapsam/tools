Web Trix
========

##target="_blank" everywhere

Single-line, jQuery script to convert all links on the page that navigate outside of the current website to create new tabs. This prevents people from accidentally closing a site by adding the `target='_blank'` attribute.

```JS
$('a[href^="http://"], a[href^="https://"]').not('a[href*="your_domain"]').attr('target', '_blank');
```
Currently only finds `<a href="">` tags with "http" and "https" that do NOT include the root directory name or domain name specified.

##clearfix
#CSS
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
#HTML
`<div class="cf"></div>`
