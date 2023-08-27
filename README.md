# HTTP Caching Cloudflare Worker

This Cloudflare Worker caches dynamically generated HTML content from your origin via the Cloudflare fetch API. 
It has also some options:

- Don´t cache on certain URL parameters.
- Don´t cache on certain browser cookies.
- Don´t cache on certain URL paths(this is also managable in Cloudflare Worker Routes => My preferred way)
- Add cookies to the users browser if certain url parameters are present. This is useful to get affiliate cookies on the run to later payout your affiliates.

THANKS to @stephan13360 for the initial code.
I have added a lot debugging stuff to better understand the behavior of the worker in certain situations. 
Those debugging outputs are visible in the live log view of Cloudflare Workers. 
BUT: In preview the caches on Cloudflares side are not active. Look here: https://developers.cloudflare.com/workers/runtime-apis/cache/
