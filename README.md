[noodle](http://noodlejs.com) 
=============================

noodle is a conigurable server and node module which individuals can use to query data from web documents like html, json and xml feeds.

```JSON
{
  "url": "https://github.com/explore",
  "selector": "ol.ranked-repositories h3",
  "extract": "text"
}
```

Features
--------

- Cross domain document querying (html, json, xml, atom, rss feeds)
- Server supports querying via JSONP and JSON POST
- Multiple queries per request
- Access to queried server headers
- Allows for POSTing to web documents
- In memory caching for query results and web documents

[http://noodlejs.com/](http://noodlejs.com/).

Server quick start
------------------

Setup

    $ npm install noodlejs

or

    $ git clone https://github.com/dharmafly/noodle.git
    $ cd noodle
    $ npm install

Start the server by running the binary

    $ bin/noodle-server
     Server running on port 8888

You may specify a port number as an argument

    $ bin/noodle-server 9090
     Server running on port 9090

Noodle as a node module
-----------------------

If you are interested in the node module just require it and check out the 
[noodle api](http://noodlejs.com/reference/#noodle-as-node-module)  

```javascript
var noodle = require('noodle');

noodle.query({
  url:      'https://github.com/explore',
  selector: 'ol.ranked-repositories h3',
  extract:  'text'
})
.then(function (results) {
  console.log(results);
});
```

Tests
-----

The noodle tests create a temporary server on port `8889` which the automated 
tests tell noodle to query against. 

To run tests you can use the provided binary *from the noodle package 
root directory*:

    $ bin/tests
