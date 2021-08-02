---
title: Cache-control headers
description: Learn how to set up cache-control headers for best use in Atlas
---

Through HTTP, `Cache-control` gives your front-end applications instructions for caching requests and responses to your app. Optimizing cache-control for Atlas will help with the deliverability of your content between the front-end and WordPress backends. To determine how to set up cache-control, see the MDN Web documentation for [Cache-control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control).

## Apps without cache-control

When you choose not to use cache-control, Atlas attempts to guess how to cache content based on the [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types). Static resources, such as CSS, Javascript, JSON, images, and videos, cache usually for 10 seconds.


## Next.js apps

Front-end applications using Next.js add immutable cache-control header resources, with `max-age` being when a resource remains in the cache in seconds. For example, any resources found in `/_next/static/` stay cached for `max-age=31536000,immutable`. Other static resources such as `/public/images/` stay cached for `max-age=0`.

For any custom resources you want to cache, add your custom headers outside of `/_next/static/`. For instructions, refer to the Vercel [headers documentation](https://nextjs.org/docs/api-reference/next.config.js/headers).


