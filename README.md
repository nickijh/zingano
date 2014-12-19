# specialtemplate

A blank(ish) template for The Denver Post's special reports layout.

## Options

There are a lot of options, whether remnants from eariler projects, or just combinations of things designed to work indepentendly or together, when you base a project on this template.

### scrollDownTo(div,offset)

Use this for internal links to scroll smoothly around the page and offset the top a bit to prevent the top of the target section/div from being hidden behind the top-bar. Example:

```
<a href="javascript:scrollDownTo('#targetdivid',45);">Link Text</a>
```

The offset (optional) is in pixels; it defaults to 60 pixels below the top of the viewport.

### Slideshows

A gallery can be built from images and loaded in-line or lazy loaded and then built with slick.js.

In the default implementation, all galleries are instantiated one-by-one on the first scroll, or on page-load if a hash is detected in the URL (i.e.: link directly to a sub-section).

The parent div just needs to have a unique ID and the `centergallery` class.

Your HTML needs to look like this:

```
<div class="centergallery" id="parentgallery">
	<div class="large-10 columns">
		<img src="http://placehold.it/1200x800&text=Gallery+Photo+1" alt="Synth mumblecore swag vinyl viral" />
		<p class="caption">Synth mumblecore swag vinyl viral. Craft beer hella squid keffiyeh, post-ironic freegan selvage 8-bit mixtape 3 wolf moon narwhal Wes Anderson viral taxidermy.</p>
	</div>
	<div class="large-10 columns">
		<img src="./img/loading.gif" data-src="http://placehold.it/1200x800&text=Gallery+Photo+2" alt="Gluten-free kale chips irony" />
		<p class="caption"><span class="captionhed">freegan forage</span> Gluten-free kale chips irony, pour-over raw denim chillwave meh swag gentrify vegan. Listicle Vice sriracha you probably haven't heard of them fixie.</p>
	</div>
	<!-- add chunks as above for each photo -->
</div>
```

#### Notes:

* Captions in Galleries are optional. the `captionhead` class can be used for a one or two word heading -- the are bold and all-caps.
* For best performance, the first image should be loaded directly in the `src` attribute. For subsequent pictures, leave the `src="./img/loading.gif"` and instead put the image URL into the `data-src` attribute. They will be lazy-loaded after the rest of the page before slick is called.
* Wrap the gallery in parent `row` and `columns` divs to fit them to the content width, or let them stand alone to make them bigger. The size of the photo is determined by the `columns` size in each individual photo block -- which should all be the same.

### Page views

You can create "pages" within the page by breaking each major section up. Wrap each "page" with an HTML `section` tag with a unique ID and an (optional) title.

```
<section id="mypage" class="omnitrig" data-omni-title="Title for Photo Gallery">
	<!-- your content -->
</section>
```

#### Notes

* The class `omnitrig` triggers a new pageview to be generated in Omniture when this section is scrolled into the viewport the first time. It is totally optional; omitting it will cause the URL in the address bar to change )and the page title if `data-omni-title` is set).
* The title in `data-omni-title` is prepended to the page title in the format "New Section Title - Project Base Title" -- with the base title being whatever the initial value of `<title>` is in the HTML.

### Tooltips

You can add a pop-up tooltip to any text by wrapping it in a span like so:

```
<span data-tooltip aria-haspopup="true" class="has-tip tip-top radius" title="This is the text that pops up when you mouse over it.">Text to hover over</span>
```

Tooltips are on-hover on the desktop, or tap-to-open on mobile/touch devices.



## Checklist



## Codebase resources
* [ZURB Foundation](http://foundation.zurb.com)
# [unveil.js](https://github.com/schneidan/unveil) (a slightly-tweaked fork)
* [slick - the last carousel you'll ever need](http://kenwheeler.github.io/slick/)
* [Mozilla Developer Network for CSS3, JS, HTML5 stuffs](https://developer.mozilla.org/‎)