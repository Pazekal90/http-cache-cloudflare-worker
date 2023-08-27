# HTTP Caching Cloudflare Worker

This Cloudflare Worker caches dynamically generated HTML content from your origin via the Cloudflare fetch API. 
It has also some options:

- Don´t cache on certain URL parameters.
- Don´t cache on certain browser cookies.
- Don´t cache on certain URL paths(this is also managable in Cloudflare Worker Routes => My preferred way)
- Add cookies to the users browser if certain url parameters are present. This is useful to get affiliate cookies on the run to later payout your affiliates.
- If there is a newer version from your origin after one visit, the next user will get this cached version. Cloudflare worker caches the newer version in the background while delivering the already cached version one last time but remarkebly faster to the user. 

We improved our TTFB(Time to first byte) Speed by factor 5 in the most cases. 
Remember: All HTML contents are the same for all of your users for those particular sites. 

HTML Request got a HIT from Cloudflare Cache as the result:
![image](https://github.com/Pazekal90/http-cache-cloudflare-worker/assets/25208775/61e669e2-b99e-4e2c-8820-370c861143fc)

THANKS to @stephan13360 for the initial code.
I have added a lot debugging stuff to better understand the behavior of the worker in certain situations. 
Those debugging outputs are visible in the live log view of Cloudflare Workers. 

BUT: In preview the caches on Cloudflares side are not active. Look here: https://developers.cloudflare.com/workers/runtime-apis/cache/
Instead you have to test with live logging to see results coming from cache. 
![image](https://github.com/Pazekal90/http-cache-cloudflare-worker/assets/25208775/15f84058-f8ae-4fde-80fc-3d3364c958f9)
