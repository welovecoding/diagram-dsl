# js-sequence-diagrams-dsl

DSL for https://github.com/bramp/js-sequence-diagrams

- [js-sequence-diagrams (gh-pages)](http://bramp.github.io/js-sequence-diagrams/)
- [js-sequence-diagrams (repository)](https://github.com/bramp/js-sequence-diagrams/)

## Demo

### Code

```js
var bart = 'Bart';
var homer = 'Homer';
var lisa = 'Lisa';
var marge = 'Marge';

var diagram = new SequenceDiagram('A Day At The Simpsons', DiagramStyle.handDrawn);
var element = $('#mySequenceDiagram');

diagram.sequences = [
  from(bart).lineTo(homer).withText('annoys'),
  from(homer).lineTo(bart).withText('chokes'),
  from(bart).dashTo(lisa).withText('annoys'),
  from(lisa).dashTo(marge).withText('stools at'),
  from(marge).lineTo(bart).withText('gives house arrest').andOpenArrow()
];

diagram.renderTo(element);
```

### Result


## Options

```ini
# Lines
->	 Normal line         lineTo(...)
-->	 Dashed line         dashTo(...)

# Arrows
->>	 Open arrow          lineTo(...).andOpenArrow()
-->> Dashed open arrow   dashTo(...).andOpenArrow()
```

## Syntax samples

```js
// Solid lines
from('A').lineTo('B').withText('Hello World');
from('A').lineTo('B').withText('Hello World').andOpenArrow();

// Dashed lines
from('A').dashTo('B').withText('Hello World');
from('A').dashTo('B').withText('Hello World').andOpenArrow();
```

## Build project

```bash
# Resolve Node.JS and Bower modules
npm install
bower install
```

