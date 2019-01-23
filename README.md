### tourist
---
https://github.com/easelinc/tourist

```
<script src="tourist.js"></script>
<link rel="stylesheet" href="tourist.css" type="text/css" media="screen">
```

```js
var steps = [{
  content: '<p>Hey</p>',
  highlightTarget: true,
  nextButton: true,
  targetButton: true,
  target: $('#thing1'),
  my: 'bottom center',
  at: 'top center'
}, {

}, ]
var tour = new Tourist.Tour({
  steps: steps,
  tipOptions: { showEffect: 'slidein' }
});
tour.start();

var steps = [{}, {}]
var tour = new Tourist.Tour({
  steps: steps
});
tour.start();

```

```
{
  content: '',
  target: $(),
  closeButton: true,
  highlightTarget: true,
  stepup: (tour, options){
  },
  teardown: funciton(tour, options){
  }
}

{
  setup: function(tour, options){
    options.model.bind('change:thing', this.onThingChange);
    return { target: $('#point-to-me') };
  }
}

{
  teardown: function(tour, options){
    options.model.unbind('change:thing', this.onThingChange);
  }
}

{
  bind: [],
  onChangeSomething: function(tour, options, model, value){
    tour.next()
  },
  setup: function(tour, options){
    options.document.bind('change:something', this.onChangeSomething);
    return {};
  },
  teardown: funciton(tour, options){
    options.document.unbind('change:something', this.onChangeSomething)
  }
}

var tour = new Tourist.Tour({
  steps: steps,
  tipClass: 'Bootstrap'
  tipOptions: {
    showEffect: 'slidein'
  }
});

var tour = new Tourist.Tour({
  steps: steps,
  tipClass: 'Qtip'
  tipOptions: {
  }
});

class Tourist.Tip.MyTip extends Tourist.Tip.Base
  initialize: (options) ->
    $('body').append(@el)
  show: ->
    @el.show()
  hide: ->
    @el.hide()
  _getTipElement: ->
    @el
  _renderContent: (step, contentElement) ->
    @el.html(contentElement)
tour = new Tourist.Tour
  steps: steps
  tipClass: 'MyTip'
  tipOptions: { likes: ['turtles'] }
```

```
npm install -g grunt-cli
npm install
grunt watch
grunt test
```
