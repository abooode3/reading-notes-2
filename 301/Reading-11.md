## OAuth
1. What is OAuth?

- it is an authentication protocol that allows you to approve one application interacting with another on your behalf without giving away your password.

2. Give an example of what using OAuth would look like.

- The simplest example of OAuth is when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s log on.

3. How does OAuth work? What are the steps that it takes to authenticate the user?

- The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

- The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

- The first site gives this token and secret to the initiating user’s client software.

- The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).

- If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

- The user approves (or their software silently approves) a particular transaction type at the first website.

- The user is given an approved access token (notice it’s no longer a request token).

- The user gives the approved access token to the first website.

- The first website gives the access token to the second website as proof of authentication on behalf of the user.

- The second website lets the first website access their site on behalf of the user.

- The user sees a successfully completed transaction occurring

4. What is OpenID?

- OpenID is about authentication, OpenID is for humans logging into machines.


## Authorization and Authentication flows
1. What is the difference between authorization and authentication?

- authentication is the process of verifying who a user is, while authorization is the process of verifying what they have access to

2. What is Authorization Code Flow?

- exchanges an Authorization Code for a token

3. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?

- The PKCE-enhanced Authorization Code Flow introduces a secret created by the calling application that can be verified by the authorization server; this secret is called the Code Verifier.

4.  What is Implicit Flow with Form Post?

- It does offer a streamlined workflow if the application needs only an ID token to perform user authentication.

5. What is Client Credentials Flow?

- the system authenticates and authorizes the app rather than a user

6. What is Device Authorization Flow?

- rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device

7. What is Resource Owner Password Flow?

- requests that users provide credentials (username and password), typically using an interactive form.