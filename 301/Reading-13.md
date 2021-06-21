# CRUD :

**1- In your own words, describe what each group of status code represents:**

- 100’s = This interim response indicates that everything so far is OK and that the client should continue the request, or ignore the response if the request is already finished.
- 200’s = The request was fulfilled.
- 300’s = The request has more than one possible response. The user-agent or user should choose one of them.
- 400’s = The request had bad syntax or was inherently impossible to be satisfied.
- 500’s = The server encountered an unexpected condition which prevented it from fulfilling the request.

**2- What is a status code 202?**

- The request has been received but not yet acted upon.

**3- What is a status code 308?**

- This means that the resource is now permanently located at another URI

**4- What code would you use if an update didn’t return data to a client?**

- 204 No Content

**5- What code would you use if a resource used to exist but no longer does?**

- 410 Gone

**6- What is the ‘Forbidden’ status code?**

- 403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

---

**1- Why do we need to pull our MongoDB database string out of our server and put it into our .env?**

- to not be published.

**2- What is middleware?**

- is software that provides common services and capabilities to applications outside of what's offered by the operating system.

**3- What does app.use(express.json()) do?**

- it is a method inbuilt in express to recognize the incoming Request Object as a JSON Object.

**4- What does the /:id mean in a route?**

- params object, with the name of the route parameter specified in the path as their respective keys

**5- What is the difference beween PUT and PATCH?**

- The main difference between the PUT and PATCH method is that the PUT method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the PATCH method supplies a set of instructions to modify the resource.

**6- How do you make a defalut value in a schema?**

- Make mongoose string schema type default value as blank and make the field optional.

**7- What does a 500 error status code mean?**

- indicates that the server encountered an unexpected condition that prevented it from fulfilling the request.

**8- What is the difference between a status 200 and a status 201?**

- The 200 status code is by far the most common returned. It means, simply, that the request was received and understood and is being processed. A 201 status code indicates that a request was successful and as a result, a resource has been created (for example a new page).

---

#### Resources :

<br>
(1)[https://en.wikipedia.org/wiki/Patch_verb]
<br>
(2)[https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500]
<br>
(3)[https://aloneonahill.com/blog/http-status-codes]
<br>
(4)[https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/]