# secheaders

HTTP Security Headers Check

## Description
Check a domain name's (passed at the command line) to see if the recommended security headers plus some additional and future/upcoming
headers are available.

## Usage
./secheaders domainname.tld

## Author 
Peter Elsner <peter.elsner@webpros.com>

## License
For cPanel's Technical Support Team. Standard cPanel, L.L.C. Copyright applies - See LICENSE.md.

## Project status
In development. Please report any problems/issues or improvements you have.


```
# ./secheaders domainname.tld
Version: 1.0.0

HTTP/2 200
server: nginx
date: Mon, 18 Jul 2022 15:09:18 GMT

Recommended Headers
========================================================================
Strict-Transport-Security - [GOOD]
    \_ strict-transport-security: max-age=31536000
X-Frame-Options - [GOOD]
    \_ x-frame-options: SAMEORIGIN
X-Content-Type-Options - [MISSING]
    \_ Add the following to the nginx.conf file:
    \_ add_header X-Content-Type-Options nosniff;
Referrer-Policy - [MISSING]
    \_ Add the following to the nginx.conf file:
    \_ add_header Referrer-Policy "no-referrer";
Permissions-Policy - [MISSING]
    \_ Add the following to the nginx.conf file:
    \_ add_header Permissions-Policy "fullscreen 'none'";
Content-Security-Policy - [MISSING]
    \_ Add the following to the nginx.conf file:
    \_ add_header Content-Security-Policy "default-src 'self';";
========================================================================
See https://support.cpanel.net/hc/en-us/articles/1500001533562 for additional information


Additional Headers
========================================================================
Access-Control-Allow-Origin - [MISSING]
Access-Control-Allow-Methods - [MISSING]
x-xss-protection - [MISSING]
========================================================================
Upcoming/Experimental Headers
========================================================================
Expect-CT - [MISSING]
Cross-Origin-Embedder-Policy - [MISSING]
Cross-Origin-Opener-Policy - [MISSING]
Cross-Origin-Resource-Policy - [MISSING]
========================================================================


# ./secheaders somedomain.tld
Version: 1.0.0

HTTP/1.1 200 OK
Server: Apache
Date: Mon, 18 Jul 2022 15:23:20 GMT

Recommended Headers
========================================================================
Strict-Transport-Security - [GOOD]
	\_ Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
X-Frame-Options - [GOOD]
	\_ X-Frame-Options: sameorigin
X-Content-Type-Options - [GOOD]
	\_ X-Content-Type-Options: nosniff
Referrer-Policy - [GOOD]
	\_ Referrer-Policy: no-referrer
Permissions-Policy - [GOOD]
	\_ Permissions-Policy: fullscreen 'none'
Content-Security-Policy - [GOOD]
	\_ Content-Security-Policy: default-src 'self';
========================================================================
See https://support.cpanel.net/hc/en-us/articles/1500001533562 for additional information


Additional Headers
========================================================================
Access-Control-Allow-Origin - [GOOD]
	\_ Access-Control-Allow-Origin: *
Access-Control-Allow-Methods - [GOOD]
	\_ Access-Control-Allow-Methods: GET, POST
x-xss-protection - [GOOD]
	\_ X-XSS-Protection: 1; mode=block
========================================================================
Upcoming/Experimental Headers
========================================================================
Expect-CT - [MISSING]
Cross-Origin-Embedder-Policy - [MISSING]
Cross-Origin-Opener-Policy - [MISSING]
Cross-Origin-Resource-Policy - [MISSING]
========================================================================
```

