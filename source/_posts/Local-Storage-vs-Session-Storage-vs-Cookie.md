---
title: Local Storage vs Session Storage vs Cookie
date: 2017-10-28 20:19:26
tags: Others
---
## LocalStorage

* Stores data **with no expiration date**, and gets cleared only through JavaScript, or clearing the Browser cache / Locally Stored Data
* Storage limit is the maximum amongst the three

## SessionStorage

* The sessionStorage object stores data **only for a session**, meaning that the data is stored until the browser (or tab) is closed.
* Data is never transferred to the server.
* Storage limit is larger than a cookie.

## Cookie
* Stores data that **has to be sent back to the server** with subsequent requests. Its expiration varies based on the type and the expiration duration can be set from either server-side or client-side (normally from server-side).
* Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
* Size must be **less than 4KB**.
* Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie