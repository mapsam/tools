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

##Mobile Menu SVG Icon

Useful SVG icon to use when building a responsive site and in need of a mobile image instead of showing the whole row. Thanks to [CSS Tricks](http://css-tricks.com/three-line-menu-navicon/) for linking me to this.

**SVG**

```HTML
<svg version="1.1" id="menu-icon" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 width="40px" height="25px" viewBox="0 0 18 12" enable-background="new 0 0 18 12" xml:space="preserve">
<path fill="none" d="z"/>
<g id="Layer_x25_201">
	<rect width="40" height="2" fill="#333333"/>
	<rect y="5" width="18" height="2" fill="#333333"/>
	<rect y="10" width="18" height="2" fill="#333333"/>
</g>
<path fill="none" d="z"/>
</svg>
```

**HTML** *(linking)*
```HTML
<img src="menu-icon.svg">
```

##target="_blank" everywhere

Single-line, jQuery script to convert all links on the page that navigate outside of the current website to create new tabs. This prevents people from accidentally closing a site by adding the `target='_blank'` attribute.

```JS
$('a[href^="http://"], a[href^="https://"]').not('a[href*="your_domain"]').attr('target', '_blank');
```

Currently only finds `<a href="">` tags with "http" and "https" that do NOT include the root directory name or domain name specified.