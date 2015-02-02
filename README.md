# fluent-plugin-out-http, a plugin for [Fluentd](http://fluentd.org)

A generic [fluentd][1] output plugin for sending logs to an HTTP endpoint.

[![Build Status](https://travis-ci.org/ento/fluent-plugin-out-http.svg?branch=master)](https://travis-ci.org/ento/fluent-plugin-out-http)

## Configuration options

    <match *>
      type http
      endpoint_url    http://localhost.local/api/
      http_method     put    # default: post
      serializer      json   # default: form
      rate_limit_msec 100    # default: 0 = no rate limiting
      raise_on_error  false  # default: true
      authentication  basic  # default: none
      username        alice  # default: ''
      password        bobpop # default: ''
      use_ssl	      true   # default: false
    </match>

## Usage notes

If you'd like to retry failed requests, consider using [fluent-plugin-bufferize][3].

----

Heavily based on [fluent-plugin-growthforecast][2]

  [1]: http://fluentd.org/
  [2]: https://github.com/tagomoris/fluent-plugin-growthforecast
  [3]: https://github.com/sabottenda/fluent-plugin-bufferize
