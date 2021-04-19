# LOCAL STORAGE

* cookies use for persistent local storage of small amounts of data:

- Cookies are included with every HTTP request, so it's slowing down web application by needlessly transmitting the same data over and over
-  sending data unencrypted over the internet (unless your entire web application is served over SSL)
- Cookies are limited to about 4 KB of data

What we really want is:
- a lot of storage space
- on the client
- that persists beyond a page refresh
- and isn’t transmitted to the server


local storage before html5
-  internet explorer, microsoft invented DHTML userData
userData: store up to 64 KB of data per domain in a hierarchical XML-based structure
- adobe introduced (flash cookies) store up to 100 KB 
- Google launched Gears
- HTML5

* HTML5 Storage: 
> it’s a way for web pages to store named key/value pairs locally, within the client web browser,data persists even after you navigate away from the web site, close your browser tab, exit your browser, or what have you.,  data is never transmitted to the remote web server .,  implemented natively in web browsers


* HTML5 STORAGE SUPPORT
- IE
- FIREFOX
- SAFARI
- CHROME	
- OPERA	
- IPHONE	
- ANDROID


 to check for HTML5 Storage:
>
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}


HTML5-> based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key.
