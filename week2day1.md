#May 30th

###Week 1 Review

We started class reviewing last week's material. Gulp seemed especially sticky so we're going to practice it by adding it to Scoreo. 

###Ipam

New repo called ipam. That's our week 9 and 10 project. Janine suggests to check that out and get familiar with it. Her friend might come soon to discuss the project and we need to be ready with questions.

##Scoreo

Janine had to create a "Week 1 brute force cleanup" branch which is exactly what it sounds like. We were very messy with our organization, and we need to communicate better. For example, we had multiple boostrap.min.css files in multiple file directories.

##Gulp

In our app directory
	-SCSS
		-sass files -> browser can't read
		-need gulp to translate into CSS
	-CSS

###Gulp Steps

	1. We need a package.json file in the root directory. Create it with "npm init" command.
	2. Use package.json to store the things we need to run gulp. "npm install" and then "npm install gulp --save-dev" will bring in Gulp and all of its dependencies. They import as node modules. It's okay to delete node modules and re-install, it's a common troubeshooting step.
	3. touch gulpfile.js 
		-var gulp = require('gulp'); <= imports gulp
		-once you have gulp, you can do gulp.task('')
		-need a default gulp.task('') 
		-run gulp in terminal by typing "gulp" (will run *only* default task)
	4. add node_modules/ directory into .gitignore file

###Sass Steps

	1. Install gulp-sass in your root directory

	npm install gulp-sass --save -dev (if you do this correctly, you'll see it in your package.json file)

	2. Create a gulp task that can find scss files:

	gulp.task('functionName', function(){
			.src('app/scss/**/*.scss') //looks for scss files in the "app/scss" directory and all other sub-directories (bc of the **)
			.pipe(sass()) //magically changes .sass to .css
			.pipe(dest(gulp.dest('dist/css')); //sends it to the "dist/css" destination
			})
	3. run in terminal using "gulp 'functionName'"

Sass uses auto-prefixer, which should make your .css compatible with any browser. If you're not sure something is compatible, use caniuse.com.
	1. npm install gulp autoprefixer --save -dev
	2. in gulpfile.js: var autoprefixer = require('gulp-autoprefixer');
	3. var autoprefixerOptions = {
  browsers: [
    'Android 2.3',
    'Android >= 4',
    'Chrome >= 20',
    'Firefox >= 24',
    'Explorer >= 8',
    'iOS >= 6',
    'Opera >= 12',
    'Safari >= 6'
  ]
}; 

###Add Bootstrap too
	1. Add @import link to beginning of main.scss
	@import "../../../node_modules/bootstrap-sass/assets/stylesheets/bootstrap";

####Version Numbering
	1.3.4 <- Major version.minor version.patch version

##Javascript
	-First project: Javascript to fetch an API from the web. We'll create a weather app to show off dis skill
		-Layout in HTML/CSS, functionality in Javascript



