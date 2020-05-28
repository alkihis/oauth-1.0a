# OAuth 1.0a Request Authorization [![semaphore][semaphore-img]][semaphore-url]

This is a port of [OAuth 1.0a package](https://github.com/ddo/oauth-1.0a) package for using in Deno.

[![Join the chat at https://gitter.im/ddo/oauth-1.0a](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ddo/oauth-1.0a?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![version][version-img]][version-url]
[![download][download-img]][download-url]
[![coverage][coverage-img]][coverage-url]
[![climate][climate-img]][climate-url]
[![dependency][dependency-img]][dependency-url]

[semaphore-img]: https://semaphoreci.com/api/v1/ddo/oauth-1-0a/branches/master/badge.svg
[semaphore-url]: https://semaphoreci.com/ddo/oauth-1-0a
[download-img]: https://img.shields.io/npm/dm/oauth-1.0a.svg?style=flat-square
[download-url]: https://www.npmjs.com/package/oauth-1.0a
[version-img]: https://img.shields.io/npm/v/oauth-1.0a.svg?style=flat-square
[version-url]: https://www.npmjs.com/package/oauth-1.0a
[dependency-img]: https://img.shields.io/david/ddo/oauth-1.0a.svg?style=flat-square
[dependency-url]: https://david-dm.org/ddo/oauth-1.0a
[coverage-img]: https://img.shields.io/coveralls/ddo/oauth-1.0a/master.svg?style=flat-square
[coverage-url]: https://coveralls.io/r/ddo/oauth-1.0a?branch=master
[climate-img]: https://img.shields.io/codeclimate/github/ddo/oauth-1.0a.svg?style=flat-square
[climate-url]: https://codeclimate.com/github/ddo/oauth-1.0a

OAuth 1.0a Request Authorization for **Deno**.

Send OAuth request with your favorite HTTP client ([request](https://github.com/mikeal/request), [jQuery.ajax](http://api.jquery.com/jQuery.ajax/)...)

No more headache about OAuth 1.0a's stuff or "oauth_consumer_key, oauth_nonce, oauth_signature...." parameters, just use your familiar HTTP client to send OAuth requests.

Tested on some popular OAuth 1.0a services:

-   Twitter
-   Flickr
-   Bitbucket
-   Openbankproject(HMAC-SHA256)

## Quick Start

```ts
import OAuth from 'https://deno.land/x/oauth-1.0a@3.0.0/mod.ts';
import { hmac } from 'https://deno.land/x/hmac@v1.0.2/mod.ts';

const oauth = new OAuth({
    consumer: { key: '<your consumer key>', secret: '<your consumer secret>' },
    signature_method: 'HMAC-SHA1',
    hash_function(base_string, key) {
        return hmac("sha1", key, baseString, "utf8", "base64").toString();
    },
})
```

Get OAuth request data that can be easily used with your http client:

```js
oauth.authorize(request, token)
```

Or if you want to get as a header key-value pair:

```js
oauth.toHeader(oauth_data)
```

For more details, see [this readme](https://github.com/ddo/oauth-1.0a/README.md);

## [Changelog](https://github.com/ddo/oauth-1.0a/releases)

## [Contributors](https://github.com/ddo/oauth-1.0a/graphs/contributors)

## License

MIT