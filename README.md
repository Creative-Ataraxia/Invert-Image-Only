# Invert Images Only


## Why

Trying to set up dark modes on everything has been a nightmare. Even though the browser’s background and texts can be set to dark-mode but the images loaded from various websites are often still blindly bright with their light background color. 

Of course you don’t wanna bother with going into the CSS to mess with each color settings directly. And just use your OS’s color setting to invert the whole screen doesn’t work because that will turn the browser in dark-mode into light-mode, missing the whole point!

So if I can only just invert the images from light to dark somehow. And the easiest solution I found was via a `Javascript’ `bookmarklet’. Here’s how:

## How

1.	Go to your browse’s `add bookmark` window; for firefox, right-click the bookmarks bar, then select `add bookmark`; for chrome, right-click the bookmarks bar, then select `add page`
2.	In the `name` box, just page something like “invert images only”; then in the `url` box under it, copy and paste this piece of `Javascript` snippet:
``` 
javascript: (() => {
  var imgs = document.getElementsByTagName("img");
  if (imgs[0].style['cssText']=="filter: invert(100%);") {
    for (var i = 0; i < imgs.length; i++) {
      imgs[i].style="filter: invert(0%);";
    }
  }
  else {
    for (i = 0; i < imgs.length; i++) {
        imgs[i].style="filter: invert(100%);";
    }
  }
})();
```
3.	Click `save`.
4.	Now go to any page with light images, after the page finish loading, select the newly created bookmark “invert images only” like you would with any regular bookmarks, and your browser will invert just the images.


Now I can read on without buring my eyes in the dead of the night anymore..
