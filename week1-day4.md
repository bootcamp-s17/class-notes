# Week 1, Day 4 Notes

##Morning Warmups
[Diagonal Difference](https://www.hackerrank.com/challenges/diagonal-difference)
[Plus Minus](https://www.hackerrank.com/challenges/plus-minus)

###Learning points from warmups

* Ternary pops up again. Early running for class favorite
* Filter method for arrays Ex: arr.filter((a) => a > 0) returns an array of items from the original array (a) that meet the condition (a >0) 

##Morning Standup

###1. Scoreboard - Cha'Sed
  * Drop down selectors
  * Player matchups
  * Hole by hole winners
  * Need for method to repeat the table to streamline code
  * Design for mobile first
  * Design to store locally and push data when connection is present
  * Gonna need some javascript to make this puppy bark
  * Not recording at this point (10:19am)
###2. Hackathon - scorecards/game entry (revisit on Friday, June 1)
  * develop multiple mockups to test for design and basic function to decide between competing choices
###3. Calendar
  1. Each user has a calendar
  2. Users can select and filter which calendars should be shown
  3. Can be modular since it is not unique to disc golf

###4. BOOTSTRAP!!!!
  * Default styles are restrictive
  * Incomplete functionality
  * Need javascript and jquery for some things
  * [Bootswatch.com](www.bootswatch.com)
    * Provides new cdn links to include different, preset themes
  * Less/Sass
    * pre-processors that let you make changes to CSS in one place
    * Less makes changes automatically. Sass needs a watcher to keep an eye on directory for changes
    * [Customize Bootstrap](getbootstrap.com/customize)

##Afternoon

###5. Organizing files 
Sometimes
  * test
    * app - files developers will use internally for workflow
      * cscc
      * index.html
    * dist - files that will be accessed by the user
      * css
      * index.html
6. Gulp
  1. Automates workflow 
  2. Downloaded node also 

NPM allows creation of package.json which saves the dependencies we've establised so that others can recreate our environment.
If you use an NPM install, good chance you need to require it in your gulpfile.js
* Holy Trinity of Sass
  1. Make a change
  2. update with Gulp
  3. Refresh browser to see change
* Set up a watcher to keep an eye on source directory so that when changes are saved in source, it will convert it to css automagically
* Watch function goes inside task function
* Need an asterisk in source filepath
* Will look at ways to shorten workflow to sub out necessary paths for other paths
*
##For tomorrow:
*Will look at including gulp into Scoreo

