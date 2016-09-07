---
layout: post
---

# Posts

## Google it for me

No thank you

```javascript
const button = document.querySelector('#buttonId');
const clickStream = Rx.Observable
                        .fromEvent(button, 'click');

const multiClickStream  = clickStream.debounce(250);

const singleClicks = multiClickStream
                        .filter(list => list.length === 1);
const doubleClicks = multiClickStream
                        .filter(list => list.length === 2);
const tripleClicks = multiClickStream
                        .filter(list => list.length === 3);
const lotsOfClicks = multiClickStream
                        .filter(list => list.length > 3);

singleClicks.subscribe(x => console.log('Single Click'));
doubleClicks.subscribe(x => console.log('Double Click'));
tripleClicks.subscribe(x => console.log('Triple Click'));
lotsOfClicks.subscribe(x => console.log('Lots of clicks'));

```
