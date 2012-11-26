# Blur.js II

Javascript library for blurring HTML content with CSS and SVG


## Usage

````
$(selector).blurjs({
    customClass: 'blurjs',
    radius: 5,
    persist: false
});
````

## About

jQuery is required, and so is a modern browser. This is nothing more than a wrapper for CSS making it easy to work with, the CSS itself will be at the bottom of this post.

<ul>
	<li><code>customClass</code>: uses this class for some of the inner workings of the script.</li>
	<li><code>radius</code>: The blur radius you want to use (int)</li>
	<li><code>persist</code>: Boolean, removes previously blurred elements.</li>
</ul>

The option <code>persist</code> is used to fix the following scenario. Instead of blurring, imagine you’re changing the opacity. If the body element has an opacity of 50%, all of its children are at 50% opacity as well. If you were then to apply 50% opacity to a child element, its opacity would actually end up being 25% of the initial value because its parent is opaque as well.

Ex. You blur the body element. Then you blur a child element, making the child extremely blurry. If <code>persist</code> is set to false, when you blur the child element, the body will become <em>unblurred</em> to allow you to have further control of how the script blurs elements.

## Resetting

````
$.blurjs('reset');
````