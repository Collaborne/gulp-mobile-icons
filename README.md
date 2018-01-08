# gulp-mobile-icons [![Build Status](https://travis-ci.org/Collaborne/gulp-mobile-icons.svg?branch=master)](https://travis-ci.org/Collaborne/gulp-mobile-icons) [![Greenkeeper badge](https://badges.greenkeeper.io/Collaborne/gulp-mobile-icons.svg)](https://greenkeeper.io/)

Gulp plugin that creates PNG icons for iOS and Android based on a SVG image.

Please read this [blog post](https://medium.com/collaborne-engineering/the-pain-of-producing-mobile-icons-and-splash-screens-and-how-to-get-rid-off-it-b37372618ea0#.up1ljd9r9) for a detailed explanation of the problem that the plugin solves.

## Usage

To use the the plugin in your gulp process:

```javascript
const gulp = require('gulp');
const mobileIcons = require('gulp-mobile-icons');

gulp.task('default', [], function() {
    gulp.src('icon.svg')
        .pipe(mobileIcons())
        .pipe(gulp.dest('images'));
});
```

This will create all icons in the folder `images/`.

### Cordova / PhoneGap

Add the following to your `config.xml` to use the icons in a Cordova/PhoneGap application:

```html
<platform name="ios">
    <!-- App icon -->
    <icon src="images/ios-57.png"      width="57"  height="57"/>
    <icon src="images/ios-57@2x.png"   width="114" height="114"/>
    <icon src="images/ios-72.png"      width="72"  height="72"/>
    <icon src="images/ios-72@2x.png"   width="144" height="144"/>
    <icon src="images/ios-60.png"      width="60"  height="60"/>
    <icon src="images/ios-60@2x.png"   width="120" height="120"/>
    <icon src="images/ios-60@3x.png"   width="180" height="180"/>
    <icon src="images/ios-76.png"      width="76"  height="76"/>
    <icon src="images/ios-76@2x.png"   width="152" height="152"/>
    <icon src="images/ios-76@3x.png"   width="228" height="228"/>
    <icon src="images/ios-83.5@2x.png" width="167" height="167"/>

    <!-- Spotlight -->
    <icon src="images/ios-50@2x.png"   width="100" height="100"/>
    <icon src="images/ios-40.png"      width="40"  height="40"/>
    <icon src="images/ios-40@2x.png"   width="80"  height="80"/>
    <icon src="images/ios-40@3x.png"   width="120" height="120"/>

    <!-- Settings -->
    <icon src="images/ios-29.png"      width="29"  height="29"/>
    <icon src="images/ios-29@2x.png"   width="58"  height="58"/>
    <icon src="images/ios-29@3x.png"   width="87"  height="87"/>

    <!-- Navigation bar and toolbar -->
    <icon src="images/ios-22.png"      width="22"  height="22"/>
    <icon src="images/ios-22@2x.png"   width="44"  height="44"/>
    <icon src="images/ios-22@3x.png"   width="66"  height="66"/>

    <!-- Tab bar -->
    <icon src="images/ios-25.png"      width="25"  height="25"/>
    <icon src="images/ios-25@2x.png"   width="50"  height="50"/>
    <icon src="images/ios-25@3x.png"   width="75"  height="75"/>
</platform>

<platform name="android">
    <icon src="images/android-ldpi.png"    density="ldpi"/>
    <icon src="images/android-mdpi.png"    density="mdpi"/>
    <icon src="images/android-hdpi.png"    density="hdpi"/>
    <icon src="images/android-xhdpi.png"   density="xhdpi"/>
    <icon src="images/android-xxhdpi.png"  density="xxhdpi"/>
    <icon src="images/android-xxxhdpi.png" density="xxxhdpi"/>
</platform>
```

### Web application

When using the app as a web application, you need to add to your `index.html` (see also [Apple documentation](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)):

```html
<!-- iPhone -->
<link rel="apple-touch-icon" href="images/ios-60@2x.png">
<!-- iPhone retina -->
<link rel="apple-touch-icon" sizes="180x180" href="images/ios-60@3x.png">
<!-- iPad -->
<link rel="apple-touch-icon" sizes="152x152" href="images/images/ios-76@2x.png">
<!-- iPad retina -->
<link rel="apple-touch-icon" sizes="167x167" href="images/ios-83.5@2x.png">
<!-- Chrome -->
<link rel="icon" sizes="192x192" href="images/chrome-192.png">
<link rel="icon" sizes="128x128" href="images/chrome-128.png">
```

## Explanation

This [blog post](https://medium.com/collaborne-engineering/take-out-the-pain-of-building-app-icons-249ee03398a4#.l6s7smjmu) explain the implementation details of this plugin.

Sample icon made by [Freepik](http://www.freepik.com) from [www.flaticon.com](http://www.flaticon.com) is licensed by [Creative Commons BY 3.0](http://creativecommons.org/licenses/by/3.0/)
