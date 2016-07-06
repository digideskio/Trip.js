> Reminder : please turn on your inspector first because we may put logs there if needed.

## Configure positions

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

<button>Run Demo</button>

