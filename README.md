# tools

Links, docs, snippets for web and software development.

### images

* https://unsplash.com/images/stock/creative-common
* https://picsum.photos/
* https://placehold.co/

### meta tags

* https://metatags.io/
* https://developers.facebook.com/tools/debug/
* https://cards-dev.twitter.com/validator
* https://www.linkedin.com/post-inspector/inspect/
* https://search.google.com/structured-data/testing-tool

### vertically centered, variable content

```CSS
.custom-div {
  position:relative; /* important for the .outer div */
  width:200px;
  height:200px;
}
.outer {
  display: table;
  position: absolute;
  width: 100%;
  height: 100%;
}
.inner {
  display: table-cell;
  vertical-align: middle;
}
```

```HTML
<div class="custom-div">
  <div class="outer">
    <div class="inner">
      <!-- Vertically centered content -->
    </div>
  </div>
</div>
```

### clearfix

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

### Mobile Menu SVG Icon

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

# Bash

### $PATH fix on Mac

Open $PATH to edit: `touch ~/.bash_profile; open ~/.bash_profile`

Add following to the file to reset bash commands: `export PATH="$HOME/.rbenv/bin:$PATH"`

You can add more commands (i.e. gdal commands) to make sure they work in your terminal environment well. 

GDAL: `export PATH=/Library/Frameworks/GDAL.framework/Programs:$PATH`

Save the file, quit the terminal to reset your environment or reset bash via: `source ~/.bash_profile`

Make sure it's working with: `echo $PATH`

### target="_blank" everywhere

Single-line, jQuery script to convert all links on the page that navigate outside of the current website to create new tabs. This prevents people from accidentally closing a site by adding the `target='_blank'` attribute.

```JS
$('a[href^="http://"], a[href^="https://"]').not('a[href*="your_domain"]').attr('target', '_blank');
```

Currently only finds `<a href="">` tags with "http" and "https" that do NOT include the root directory name or domain name specified.

### CSS3 transitions

Transition any change to the element's style by placing the cross-browser specifications to the element's CSS properties.

```CSS
-webkit-transition: 0.2s;
-moz-transition: 0.2s;
-ms-transition: 0.2s;
-o-transition: 0.2s;
transition: 0.2s;
```

##Change properties based on scroll height (jQuery)

I use this for changing a page element's CSS properties when the user scrolls down. Good for changing properties on menus to keep them sticky or change their size.

```JS
$(window).scroll(function() {
	var scroll = $(window).scrollTop();
	if ( scroll < 40 ) { //page height variable
		$("#element").css({'your css properties'});
	}
	else {
		$("#element").css({'your css properties back to normal'});
	}
});
```

##Box Sizing: Border Box

Prevent borders and padding form expanding beyond the bounds of your container element in CSS (i.e. it pushes the padding inwards).

```CSS
box-sizing:border-box;	
-moz-box-sizing:border-box;	
-webkit-box-sizing:border-box;
```

##Full Cover Background CSS

Ensure a background image covers the entire element space.

```CSS
-webkit-background-size: cover; 
-moz-background-size: cover; 
-o-background-size: cover; 
background-size: cover;
```

##Standard Media Queries

Just a quick set of media queries to start with when building a responsive website.

```CSS
@media (min-width: 996px) {
}

@media (max-width: 995px) and (min-width: 768px) {
}
 
@media (max-width: 767px) and (min-width: 481px) { 
}

@media (max-width: 480px) { 
}
```

##HTML <meta> tag for Media Queries

In order for you mobile devices to correctly use your `@media` queries you'll have to make sure the `<meta>` tag is set appropriately.

```HTML
<meta name="viewport" content="width=device-width, initial-scale=1.0;">
```

