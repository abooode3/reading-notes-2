### Spring Security Architecture

* Application security boils down to two more or less independent problems:
 - authentication (who are you?) 
 - authorization (what are you allowed to do?)



 * Authentication:

public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}


- An AuthenticationManager can do one of 3 things in its authenticate() method:

1. Return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.

2. Throw an AuthenticationException if it believes that the input represents an invalid principal.

3. Return null if it cannot decide

- AuthenticationException is a runtime exception. It is usually handled by an application in a generic way, depending on the style or purpose of the application


- The most commonly used implementation of AuthenticationManager is ProviderManager, but it has an extra method to allow the caller to query whether it supports a given Authentication type:

public interface AuthenticationProvider {

	Authentication authenticate(Authentication authentication)
			throws AuthenticationException;

	boolean supports(Class<?> authentication);
}

- Class<? extends Authentication>
- ProviderManager can support multiple different authentication mechanisms in the same application by delegating to a chain of AuthenticationProviders
- ProviderManager has an optional parent, which it can consult if all providers return null. If the parent is not available, a null Authentication results in an AuthenticationException.


#### Authorization or Access Control
* Once authentication is successful, we can move on to authorization

- An AccessDecisionVoter considers an Authentication (representing a principal) and a secure Object, which has been decorated with ConfigAttributes:

boolean supports(ConfigAttribute attribute);

boolean supports(Class<?> clazz);

int vote(Authentication authentication, S object,
        Collection<ConfigAttribute> attributes);

- Object is completely generic in the signatures of the AccessDecisionManager and AccessDecisionVoter
-  ConfigAttributes are also fairly generic, representing a decoration of the secure Object with some metadata that determines the level of permission required to access it


### Web Security
* Spring Security in the web tier (for UIs and HTTP back ends) is based on Servlet Filters, so it is helpful to first look at the role of Filters
1.  client sends a request to the application
2. the container decides which filters and which servlet apply to it based on the path of the request URI
3. one servlet can handle a single request, but filters form a chain, so they are ordered
4. filter can also modify the request or the response used in the downstream filters and servlet
5. The order of the filter chain is very important, and Spring Boot manages it through two mechanisms: @Beans of type Filter can have an @Order or implement Ordered
6. Spring Security is installed as a single Filter in the chain

- Method Security
As well as support for securing web applications, Spring Security offers support for applying access rules to Java method executions.

- The first step is to enable method security
@SpringBootApplication
@EnableGlobalMethodSecurity(securedEnabled = true)
public class SampleSecureApplication {
}

- Then we can decorate the method resources directly:

@Service
public class MyService {

  @Secured("ROLE_USER")
  public String secure() {
    return "Hello Security";
  }

}


- Working with Threads
Spring Security is fundamentally thread-bound, because it needs to make the current authenticated principal available to a wide variety of downstream consumers. The basic building block is the SecurityContext, which may contain an Authentication (and when a user is logged in it is an Authentication that is explicitly authenticated)

SecurityContext context = SecurityContextHolder.getContext();
Authentication authentication = context.getAuthentication();
assert(authentication.isAuthenticated);

- If you need access to the currently authenticated user in a web endpoint, you can use a method parameter in a @RequestMapping, as follows:

@RequestMapping("/foo")
public String foo(@AuthenticationPrincipal User user) {
  ... // do stuff with user
}