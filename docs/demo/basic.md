> Reminder : please turn on your inspector first because we may put logs there if needed.

# Change position

<button>Run this demo</button>

```javascript
var trip1 = new Trip([
  { sel : $(".demo-basic-1.step1"), content : "North", position : "n" },
  { sel : $(".demo-basic-1.step2"), content : "East",  position : "e" },
  { sel : $(".demo-basic-1.step3"), content : "South", position : "s" },
  { sel : $(".demo-basic-1.step4"), content : "West",  position : "w" }
], {
  
});

$(".start-demo-basic-1").on("click", function() {
  trip1.start();
});
```

Check its [documentation](../documentations/configuration.md#position) for more supported positions.

# Change theme

```javascript
var trip2_1 = new Trip([
  { sel : $(".demo-basic-2.step1"), content : "North", position : "n" },
  { sel : $(".demo-basic-2.step2"), content : "East",  position : "e" },
  { sel : $(".demo-basic-2.step3"), content : "South", position : "s" },
  { sel : $(".demo-basic-2.step4"), content : "West",  position : "w" }
], {
  tripTheme : "white",
  onStart : function() {
    $("body").css({ "background-color" : "#eee" });
  },
  onEnd : function() {
    $("body").css({ "background-color" : "#fff" });
  }
});

$(".start-demo-basic-2-1").on("click", function() {
  trip2_1.start();
});
```

Check its [documentation](../documentations/configuration.md#triptheme) for more supported themes.

# Scoll top top when finished

```javascript
var trip3 = new Trip([
  { sel : $(".demo-basic-3.step1"), content : "Let's fly ...", position : "e" }
], {
  backToTopWhenEnded : true,
  delay : 3000
});

$(".start-demo-basic-3").on("click", function() {
  trip3.start();
});
```

Check its [documentation here](../documentations/configuration.md#backtotopwhenended).

# Show close box and navigation buttons

```javascript
var trip4 = new Trip([
  { sel : $(".demo-basic-4.step1"), content : "Hola!", position : "n" },
  { sel : $(".demo-basic-4.step2"), content : "Adios!", position : "s" }
], {
  showNavigation : true,
  showCloseBox : true,
  delay : -1
});

$(".start-demo-basic-4").on("click", function() {
  trip4.start();
});
```

Check documentation about [showNavigation](../documentations/configuration.md#shownavigation) and [showCloseBox](../documentations/configuration.md#showclosebox)

** Note: ** When enabling `showNavigation`, sometimes it means that you don't need the countdown timer ! Users will mainly use navigation buttons to go next / previous. So don't forget to set `delay` to `-1` to disable it.

# Global options

```
var trip5 = new Trip([
  { sel : $(".demo-basic-5.step1"), content : "Hi", position : "n" },
  { sel : $(".demo-basic-5.step2"), content : "Press ESC to stop this step !", position : "s", delay : 3000, myFunction : function() { return "this is user's function"; } },
  { sel : $(".demo-basic-5.step3"), content : "Click the close icon to see what's going on in your console log", delay: -1, showCloseBox: true }
], {
  onStart : function() {
    console.log("onStart");
  },
  onEnd : function() {
    console.log("onEnd");
  },
  onTripStop : function() {
    console.log("onTripStop");
  },
  onTripChange : function(i, tripData) {
    if ( i === 1 ) {
      console.log("You can put your own function or data in tripData andaccess it onTripChange !");
      console.log("current tripIndex : " + i);
      console.log("current tripData : ", tripData);
      console.log("User's function : " + tripData.myFunction());
    }
  },
  onTripClose: function(i) {
    console.log("You close the trip at index : ", i);
  }
});

$(".start-demo-basic-5").on("click", function() {
  trip5.start();
});
```

Check its [documentation here](../documentations/configuration.md#global-options).

# Local options

> Supported after 2.0.0+

```javascript
var trip6 = new Trip([
  { 
    sel: $('.demo-basic-6.step1'),
    content: 'onTripStart will be called when entering this trip',
    onTripStart: function(tripIndex) {
      console.log('onTripStart : ', tripIndex);
    },
    onTripEnd: function(tripIndex) {
      console.log('onTripEnd : ', tripIndex);
    }
  },
  {
    sel: $('.demo-basic-6.step2'),
    content: 'We will use global onTripStart if there is no local one'
    onTripEnd: function(tripIndex) {
      console.log('onTripEnd : ', tripIndex);
    }
  }
], {
  onTripStart: function(tripIndex) {
    console.log('default onTripStart : ', tripIndex);
  }
});

$('.start-demo-basic-6').on('click', function() {
  trip6.start();
});
```

Check its [documentation here](../documentations/configuration.md#local-options).

**Note :** If local options exist, then global options will be suppressed by default !

# Highlight target

```
var trip7 = new Trip([
  { sel : $(".demo-basic-7.step1"), content : "Highlight this", expose : true },
  { sel : $(".demo-basic-7.step2"), content : "Highlight multiple elements with selector or jQuery object", expose : '.demo-basic-7.step1, .start-demo-basic-7' },
  { sel : $(".demo-basic-7.step3"), content : "No highlight" },
  { sel : $(".demo-basic-7.step4"), content : "Highlight that", expose : true }
], {
  delay : 3000
});

$(".start-demo-basic-7").on("click", function() {
  trip7.start();
});
```

Check its [documentation here](../documentations/configuration.md#expose).

# Animation

> Powered by animate.css

```javascript
var trip8 = new Trip([
  { sel : $(".demo-basic-8.step1"), content : "hi"},
  { sel : $(".demo-basic-8.step2"), content : "hi", animation: 'bounce'},
  { sel : $(".demo-basic-8.step3"), content : "hi", animation: 'shake'},
  { sel : $(".demo-basic-8.step4"), content : "hi", animation: 'fadeIn'},
  { sel : $(".demo-basic-8.step5"), content : "hi", animation: 'fadeInUp'},
  { sel : $(".demo-basic-8.step6"), content : "hi", animation: 'fadeInDown'},
  { sel : $(".demo-basic-8.step7"), content : "hi", animation: 'fadeInLeft'},
  { sel : $(".demo-basic-8.step8"), content : "hi", animation: 'rotateInUpRight'}
], {
  delay : 3000,
  animation: 'tada'
});

$(".start-demo-basic-8").on("click", function() {
  trip8.start();
});
```

Check its [documentation and supported animations here](../documentations/configuration.md#animation).
