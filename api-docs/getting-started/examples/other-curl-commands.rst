.. _gsg-other-curl-commands:

Other cURL commands 
~~~~~~~~~~~~~~~~~~~

You can issue any of the REST requests defined for Cloud Block Storage
with the cURL utility.

Note that generally each time ``cURL`` is invoked to perform an
operation, a separate TCP/IP and SSL connection is created and then
discarded. The language APIs, in contrast, are designed to reuse
connections between operations and therefore provide much better
performance. We recommend that you use one of the language APIs (for
example, Python or Ruby) in your production applications and limit cURL
to quick-and-easy testing and troubleshooting.
