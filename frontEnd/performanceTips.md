# Performance Tips

Few ways to optimize performance:

* Minimize requests / concatenation. Try to combine requests into a single one.
* Compress/Minify CSS and JS files.
* Use SVG sprites where possible. Data URIs?

Ways to optimize images:
  * Lossy - lowers image quality
  * Lossless - doesn't affect quality.

1) Compress images using lossy method (resizing images to size no bigger than needed.) then export at slightly lower quality without compressing too much.
2) run images through optimization tool like ImageOptim to remove unnecessary information such as metadata.

* Avoid 'render-blocking' JS and CSS files which are files that need to be loaded and processed before the browser can display any information.

* Gzipping

* Caching / Cache-busting

[PageSpeed Test Tool] (https://search.google.com/search-console/mobile-friendly?utm_source=psi&utm_medium=link&utm_campaign=psi-ux-banner&hl=en-US)
