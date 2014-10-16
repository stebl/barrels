# Simple DB Fixtures for Sails.js (^0.10.x) with Associations Support

[![Build Status](https://travis-ci.org/bredikhin/barrels.png?branch=master)](https://travis-ci.org/bredikhin/barrels)
[![Dependency Status](https://gemnasium.com/bredikhin/barrels.png)](https://gemnasium.com/bredikhin/barrels)


## Installation

`$ npm i --save-dev barrels`

## Usage

Drop your fixtures in `test/fixtures` as JSON files named after your models.

Once your [Sails.js](http://sailsjs.org/) server is started:

    var Barrels = require('barrels');
    var barrels = new Barrels();
    var fixtures = barrels.data;
    barrels.populate(function(err) {
      ...
    });

Pass to the constructor the path to the folder containing your fixtures
(defaults to `./test/fixtures`).

`Populate`'ing the test database involves three steps:

* Removing any existing data from the collection corresponding to the fixture
* Loading the fixture data into the test database
* Automatically applying associations (can be disabled by passing `false` as second parameter to `populate`)

## Automatic association

Use the number of position (starting from one) of an entry in the JSON fixture
as a reference to associate models (see
https://github.com/bredikhin/barrels/blob/master/test/fixtures/products.json
for example). This feature can be disabled by passing `false` as second parameter to `populate`.

## Dependencies

* [Async.js](https://github.com/caolan/async)
* [Lo-Dash](http://lodash.com/)

## License

[The MIT License](http://opensource.org/licenses/MIT)

Copyright (c) 2013-2014 [Ruslan Bredikhin](http://ruslanbredikhin.com/)
