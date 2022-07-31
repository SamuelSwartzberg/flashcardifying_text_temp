For HTTP APIs, the endpoint is most commonly an URL + request verb.

### REST

⟮REST⟯ is short for ⟮Representational State Transfer⟯
⟮REST⟯ is a set of ⟮constraints⟯/⟮design principles⟯ for ⟮APIs⟯
⟮REST⟯ as an idea was created in ⟮2000⟯ by ⟮Roy Fielding⟯ in his ⟮doctoral dissertation⟯
On a theoretical level, ⟮REST⟯ consists of ⟮6⟯ ⟮constraints/criteria⟯.
While REST is theoretically implementation-independent, REST APIs generally transmit their data over HTTP as JSON
sometimes, HTTP APIs are called REST APIs even if they don't follow all constraints
an API following REST is often called RESTful
for the client-server constraint of REST to be met, client and server should be independent of each other, as long as the interface is not altered
Code on demand as a REST API constraint means that a REST endpoint may return code to execcute
RESTful APIs must be stateless, that is, the server does not have state, but rather any state information is transmitted by the client
The thing a RESTful API returns is called aaresource

#### six principles (alphabetical)

Cacheability
Client-server achitecture/decoupling
Code on demand
Layered system architecture
Statelessness
Uniform interface

#### HATEOAS

HATEOAS = Hypermedia as the Engine of Application State
HATEOAS(Hypermedia as the Engine of Application State) is part of the uniform interface constraint of REST
HATEOAS requires the responses of an API to contain all the relevant hyperlinks for further requests/action
in a RESTful API following HATEOAS, the API may change its URLs without creating incompatibilites
in a RESTful API following HATEOAS, one hits an initial API URL and navigates via hyperlinks from there.
Access in a RESTful API following HATEOAS is similar to a web-browsing user hitting a home page and finding their way from there

### OAuth

OAuth is short for Open Authorization
The current version of OAuth  is OAuth 2
Most APIs use OAuth for granting access to them, e.g. to monitor access and enforce API limits.
OAuth is also commonly used to grant access to information of other accounts without giving up your password.
OAuth is often used for logging in with Facebook, GitHub, Google, etc.
In OAuth there are 4 roles/actors, the resource owner (= User), the client (= Application), Resource Server (= Where the accounts are located), and Authorization Server
in OAuth, any client (= application) needs to register themselves with a resource server.
When registering an application with a resource server, one needs to provide a callback URL, which is where the resource server will redirect users after registering. 
After registering an applicationwith the resource server, it will issue a client ID and secret.
the client ID is public, the secret must be kept private.
client ID and secret are functionally the username and password of the application
The permissions to be granted or not in OAuth are known as scopes.
While the flow of OAuth using redirection etc. is the most common flow, there are others

OAuth 2.0 (grant type: Authorization code)

flex-container:✫tmp7t5et6aw.png✫

TODO transorm flow into ascii art maybe

In general, when users want to sign in using OAuth:
1. the application makes a request using its client id
2. The user sees a screen asking them to grant access
3. The user clicks ok (or not) and is redirected
4. We get an authorization code
5. We exchange the authorization code for an access token
6. We can now make API requests
