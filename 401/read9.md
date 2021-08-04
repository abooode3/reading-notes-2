### The HTTP Request Lifecycle

 * Step 1: Local Processing
 - Depending on how in depth you want to get, much can happen during this step depending on the application making the request

 * Step 2: Resolve an IP
- The DNS request contains the preconfigured IP for your DNS server and your return IP in its header.
- Once your request arrives at your configured DNS server, the server looks for the address associated with the requested hostname.

* step 3: Establish a TCP Connection: 
- having a completed three-way handshake and an established connection where both the client and server have received acknowledgment of the connection from the other party.

* Step 4: Send an HTTP Request
- the resource being requested, and the protocol version. The header of the request is made up of pairs in the form name:value <CR><LF>

* Step 5: Tearing Down and Cleaning Up
- Once the response has been fully delivered, the client sends a FIN packet at the TCP level, to which the server responds with an ACK


###### way of performing HTTP requests in Java — by using the built-in Java class HttpUrlConnection. 

-  HttpUrlConnection: the code can be more cumbersome than other HTTP libraries and that it does not provide more advanced functionalities such as dedicated methods for adding headers or authentication.

- Creating a Request : We can create an HttpUrlConnection instance using the openConnection() method of the URL class

- Adding Request Parameters : If we want to add parameters to a request, we have to set the doOutput property to true, then write a String of the form param1=value¶m2=value to the OutputStream

- Setting Request Headers

- Configuring Timeouts : HttpUrlConnection class allows setting the connect and read timeouts

- Handling Cookies

- Handling Redirects : We can enable or disable automatically following redirects for a specific connection by using the setInstanceFollowRedirects() method with true or false parameter

- Reading the Response : Reading the response of the request can be done by parsing the InputStream of the HttpUrlConnection instance.

-  Reading the Response on Failed Requests

- Building the Full Response


