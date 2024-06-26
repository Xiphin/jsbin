**IMPORTANT:** this current version of jsbin (v4.x.x) is no longer actively maintained and the new version of jsbin (v5) is currently in active development. This means that pretty much all the docs in this repo will be soon out of date. Please be warned ❤️

☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️☝️

---

# JS Bin

JS Bin is an open source collaborative web development debugging tool.

## If you use JS Bin locally...

It likely means you're not going to subscribe as a pro user - which is how we're sustaining our project, which is cool, but [please consider donating via OpenCollective here](https://opencollective.com/jsbin/contribute).

## What can JS Bin do?

* Write code and have it both save in real-time, but also render a full preview in real-time
* Help debug other people's JavaScript, HTML or CSS by sharing and editing urls
* CodeCast - where you share what you're typing in JS Bin in real-time
* Remote rendering - view the output of your JS Bin on any device on any platform, updating in real-time
* Processors, including: coffee-script, LESS, Markdown and Jade.
* Debug remote Ajax calls

Find out more about JS Bin's features via the [YouTube JS Bin playlist](http://jsbin.com/videos).

## Who built this?

JS Bin was built by [Remy Sharp](http://remysharp.com) and is completely open source and available at [http://github.com/jsbin/jsbin](http://github.com/jsbin/jsbin). You can also follow [@rem](http://twitter.com/rem) on Twitter where he'll tweet about JavaScript, HTML 5 and other such gems.

If you would like to work with Remy and his company, [Left Logic](http://leftlogic.com) on a front end development project, [please get in touch](http://leftlogic.com/contact?message=Found%20through%20jsbin.com).

UX was kindly donated by [Danny Hope](http://yandleblog.com) who also tweets as [@yandle](http://twitter.com/yandle).

The vast majority of the port from PHP to Node in June 2012 was done by [Aron Carroll](http://aroncarroll.com/) who also plays in github as [@aron](http://github.com/aron).

## A short history

[JS Bin](http://jsbin.com) is a webapp specifically designed to help JavaScript and CSS folk test snippets of code, within some context, and debug the code collaboratively.

JS Bin allows you to edit and test JavaScript and HTML (reloading the URL also maintains the state of your code - new tabs doesn't). Once you're happy you can save, and send the URL to a peer for review or help. They can then make further changes saving anew if required.

The original idea spawned from a conversation with another developer in trying to help him debug an Ajax issue. The original aim was to build it using Google's app engine, but in the end, it was [John Resig](http://ejohn.org)'s [Learning app](http://ejohn.org/apps/learn) that inspired me to build the whole solution in JavaScript with liberal dashes of jQuery and a tiny bit of LAMP for the saving process.

[Version 1](http://1.jsbin.com) of [JS Bin](http://www.flickr.com/photos/remysharp/4284906136) took me the best part of 4 hours to develop [back in 2008](http://remysharp.com/2008/10/06/js-bin-for-collaborative-javascript-debugging/), but [version 2](http://2.jsbin.com) was been rewritten from the ground up and is completely [open source](http://github.com/remy/jsbin).

## Build Process

JS Bin has been designed to work both online at [jsbin.com](http://jsbin.com) but also in your own locally hosted environment - or even live in your own site (if you do host it as a utility, do let us know by pinging [@js_bin](http://twitter.com/js_bin) on twitter).

Historically JS Bin was built on PHP, but has since moved to Node. The PHP flavour is no longer supported, however everything else [released in v3.0.0](https://github.com/jsbin/jsbin/tags) of JS Bin is available in both, but all releases after are only supported in the Node environment. Your PHP mileage may vary!

For detailed instructions on how to build JS Bin please see the [running your own JS Bin document](/docs/running-your-own-jsbin.md).

If you install [Node.js](http://nodejs.org) installation is easy:

    $ npm install -g jsbin
    $ jsbin

Optionally point JS Bin to your config:

    $ JSBIN_CONFIG=~/config.local.json jsbin

Then open your browser to [http://localhost:3000](http://localhost:3000) and you have a fully working version of JS Bin running locally.

## API

A simple REST based API exists for anonymous users if it is enabled in your config.\*.json, or can be restricted to registered users with a key specified in `ownership.api_key`

Authentication is required for all API requests unless one of the following api configuration options are set:

- `api.allowAnonymousReadWrite` - if set to true allows GET and POST operations to the API anonymously (without an API key)
- `api.allowAnonymousRead` - if set to true allows GET operations to the API anonymously (without an API key)

By default, `config.default.json` has `api.allowAnonymousRead` set to true.

Curl authentication examples:

```
$ curl http://{{host}}/api/:bin -H "Authorization: token {{token_key}}"
$ curl http://{{host}}/api/:bin?api_key={{token_key}}
```

End points are:

- `GET /api/:bin` - Retrieve the latest version of the bin with that specified ID
- `GET /api/:bin/:rev` - Retrieve the specific version of the bin with the specified ID and revision
- `POST /api/save` - Create a new bin, the body of the post should be URL encoded and contain `html`, `javascript` and `css` parameters
- `POST /api/:bin/save` - Create a new revision for the specified bin, the body of the post should be URL encoded and contain `html`, `javascript` and `css` parameters

## Backers

[Become a backer]((https://opencollective.com/jsbin/contribute)) and show your support to our open source project.


## Sponsors

Does your company use JS Bin? Ask your manager or marketing team if your company would be interested in supporting our project. Support will allow the maintainers to dedicate more time for maintenance and new features for everyone. Also, your company's logo will show [on GitHub](https://github.com/jsbin/jsbin#readme) --who doesn't want a little extra exposure?  [Here's the info](https://opencollective.com/jsbin/contribute).
