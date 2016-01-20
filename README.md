frontend-nanodegree-website-optimisation
===============================


#### Critical Rendering Path for index.html:

### 1. CSS 
Added all 'above-the-fold' CSS styling to the index.html file via the style tag. Minified using gulp-cssnano.

### 2. Javascript
Relocated GoogleAnalyticsObject script to it's own js file. Added the async property to each of the Javascript file references. Minified using uglify.

### 3. Images
Saved all files locally. Used Photoshop to 'Save for Web' to reduce file size. Resized 'pizzeria.jpg' image to match the others. Compressed images using gulp-imagemin.

### 4. HTML
Replaced custom font with Helvetica. 

### 5. Performance Scores
PageSpeed Insights score (via github gh-pages branch): Desktop - 95  Mobile - 92. 



#### Framerate for pizza.html

1. Reduced the total number of generated sliding pizzas by half (from 200 to 100).

2. Replaced '.querySelectors' with more specific 'getElementsBy...'.

3. Removed scrollTop variable from the updatePositions for loop, since it remains static whilst the function executes.

4. Cached the length of the items array, since the total number of pizzas on the page remains constant.

5. Created a for loop to store each of the five repeating phase values in the 'phaseValues' array.

6. Time to generate last ten frames via MAMP's localhost:8888 - <1ms.


#### Computational Efficiency for pizza.html

1. Replaced '.querySelectors' with more specific 'getElementsBy...'.

2. Removed newSize & windowWidth variables, and replaced them with their former values when determining var 'oldSize' (line 410) & 'dx' (line 434).

3. Integrated the changeSliderLabel() with the sizeSwitcher() function. 

4. Relocated 'dx' and 'newWidth' outside of the for loop inside the changePizzaSizes() function, since both only need to be calculated once. 

5. Time to resize pizzas via MAMP's localhost:8888 - ~1ms.


#### Build Tools 

1. Installed gulp-cssnano to minify the project css files. 

2. Installed gulp-imagemin to compress all images to reduce file size. 

3. Installed gulp-uglify to minify all JS files. 

4. Installed gulp-plumber to prevent the watch task from crashing if a fault was discovered. 

5. Local server was setup by installing MAMP (https://www.mamp.info/en/), using the url localhost:8888.


#### Comments  

1. All optimisations can be viewed by searching for 'P4 Optimisation:' in the views/main.js file.
