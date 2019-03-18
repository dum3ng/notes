# CORS and credential

CORS 作为浏览器的一种安全机制，对请求作出了一些限制。
例如， when the _CORS_ is set to wildcard `*`, then the credential mode of request
can not be `include`.
This is because the wildcard `*` will allow any site to make `POST` request to
the server, and if the credential mode is `include`, the request will include
the credentials, i.e. https cookies, which is not the credentials of the server site,
and if an attacker on another site has a valid session data for the original site,
he/she can make dangerous action with post request.

So we need to set the credential mode of the request to `same-origin` or `omit`
when the `Cross Origin Request Site` is `*`.
