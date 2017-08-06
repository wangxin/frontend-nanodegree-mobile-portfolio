## Website Performance Optimization portfolio project

Thanks to Github Pages, website of this project can be viewed at: [https://wangxin.github.io/frontend-nanodegree-mobile-portfolio/](https://wangxin.github.io/frontend-nanodegree-mobile-portfolio/)

### How to build an optimized version of the website of this project

1. Ensure that Node and npm are installed
```
node -v
npm -v
```
2. Install gulp-cli
```
npm install --global gulp-cli
```
3. Download the project and install build tools
```
git clone https://github.com/wangxin/frontend-nanodegree-mobile-portfolio.git
cd frontend-nanodegree-mobile-portfolio
npm install
```
4. Run the build tool. Optimized version of the website will be stored in `dist` subfolder.
```
gulp
```

### How to inspect the site on local machine

1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/frontend-nanodegree-mobile-portfolio/dist
  $> python -m SimpleHTTPServer 8080
  ```

### Make your local site accessible from Internet
1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the dist folder of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/frontend-nanodegree-mobile-portfolio/dist
  $> ./ngrok http 8080
  ```

### Optimizations made in `index.html`:

* Do not use google font
* Add `media=”print”` attribute for `css/print.css`
* Inline `css/style.css` in `index.html`
* Add `async` attribute for the scripts
* Use Google optimized image and js files 
* Move inline script to the end of document

### Optimizations made in `views/js/main.js`:

#### Improve render performance to 60fps
* Read and store `document.body.scrollTop` property before the loop to avoid repetitive layout triggered by reading `document.body.scrollTop` in the loop. Huge improvement
* Reduce the number of moving pizza from 200 to 40. Improved a little bit.
* Get all moving pizza elements by querying the parent element and reading its children. Tiny improvement

#### Improve pizza resize performance to less than 5ms

* Move querying pizza container elements out of loop
* Discard the existing resizing algorithm `determineDx`
* Simply use relative width 25%, 33.33% and 50% to resize pizzas
* Move querying the resize slider element out of the switch statement
