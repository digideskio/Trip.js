# Theme

In Trip.js, we do support five built-in themes for devs to use ! They have different looks and feels so just choose whichever you like for your works :)

## Black

## White

## Dark

## Yeti

## Minimalism

# Theme details

Go check [theme folder](https://github.com/EragonJ/Trip.js/tree/master/src/themes) first, you will notice there are several default themes got supported by Trip.js. If you check the `default` one as reference, you will see the theme structure below : 

```javascript
module.exports = [
  '<div class="trip-block">',
    '<a href="#" class="trip-close"></a>',
    '<div class="trip-header"></div>',
    '<div class="trip-content"></div>',
    '<div class="trip-progress-steps"></div>',
    '<div class="trip-navigation">',
      '<a href="#" class="trip-prev"></a>',
      '<a href="#" class="trip-skip"></a>',
      '<a href="#" class="trip-next"></a>',
    '</div>',
    '<div class="trip-progress-bar"></div>',
  '</div>'
].join('');
```

As you can see, a theme will be composed with several components :

## .trip-block

This is the main container for all components, so if you want to customize your own theme later, you need to make sure to use `.trip-block.YOUR_TRIP_CLASS_NAME` to override the default styles.

## .trip-close

This is the UI for users to *click* and to close the whole trip. when clickin on this, `onTripClose()` callback will be triggered and you can some follow-up works there.

## .trip-header
## .trip-content
## .trip-progress-steps
## .trip-navigation
## .trip-prev
## .trip-skip
## .trip-next
## .trip-progress-bar

# How to make a new theme 

It's awesome that you are reading this part ! 
