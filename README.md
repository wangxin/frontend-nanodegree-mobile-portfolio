## Website Performance Optimization portfolio project

Thanks to Github Pages, website of this project can be viewed at: [https://wangxin.github.io/frontend-nanodegree-mobile-portfolio/](https://wangxin.github.io/frontend-nanodegree-mobile-portfolio/)

### Optimizations made in `index.html`:

* Do not use google font
* Add `media=”print”` attribute for `css/print.css`
* Inline `css/style.css` in `index.html`
* Add `async` attribute for the scripts
* Use Google optimized image and js files 
* Move inline script to the end of document

## Optimizations made in `views/js/main.js`:

* Read and store `document.body.scrollTop` property before the loop to avoid repetitive layout triggered by reading `document.body.scrollTop` in the loop. Huge improvement
* Reduce the number of moving pizza from 200 to 40. Improved a little bit.
* Get all moving pizza elements by querying the parent element and reading its children. Tiny improvement
