---
title: Timer
tags: date,begginer
---

Shows a timer to a specific date and a message when time's up

- Use `Date.prototype.getTime()` to get time of timer end and start.
- Calculate the time difference between start and end time
- If the current `date` is past the countdown date display a simple message instead.

```js
let x = setInterval( function = (id, countDownDate, timerEndText) => {
    let waitdate = new Date(countDownDateString).getTime();
    let rightnow = new Date().getTime();
    var distance = waitdate - rightnow;
    var days = Math.floor( distance / ( 1000 * 60 * 60 * 24 ));
    var hours = Math.floor(( distance % ( 1000 * 60 * 60 * 24 )) / ( 1000 * 60 * 60 ));
    var min = Math.floor(( distance % ( 1000 * 60 * 60)) / ( 1000 * 60 ));
    var sec = Math.floor(( distance % ( 1000 * 60 )) / 1000);
    document.getElementById(id).innerHTML = days + "d " + hours + "h " + min + "m " + sec + "s";
    if ( distance < 0 ) {
        clearInterval(x);
        document.getElementById(id).innerHTML = "";
    }
}, 1000);
```

```js
setInterval('elementId', 'Oct 31, 2020 00:00:00', 'Wait is Over'), 5); // 'Oct 31, 2020'
setInterval('elementId1', 'Oct 21, 2020 00:00:00', 'Lets begin'), 5); // 'Oct 21, 2020'
```