##### Spring MVC and Thymeleaf: how to access data from templates

#### Spring
- The Spring Framework is an application framework and inversion of the control container for the Java platform. The framework’s core features can be used by any Java application, but there are extensions for building web applications on top of the Java EE platform

- @Controller classes are responsible for preparing a model map with data and selecting a view to be rendered. This model map allows for the complete abstraction of the view technology and, in the case of Thymeleaf, it is transformed into a Thymeleaf context object


1. Spring model attributes
> Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes
- Add attribute to Model via its addAttribute method:

   @RequestMapping(value = "message", method = RequestMethod.GET)
        public String messages(Model model) {
            model.addAttribute("messages", messageRepository.findAll());
            return "message/list";
        }
- Return ModelAndView with model attributes included:

    @RequestMapping(value = "message", method = RequestMethod.GET)
        public ModelAndView messages() {
            ModelAndView mav = new ModelAndView("message/list");
            mav.addObject("messages", messageRepository.findAll());
            return mav;
        }
- Expose common attributes via methods annotated with @ModelAttribute:

    @ModelAttribute("messages")
        public List<Message> messages() {
            return messageRepository.findAll();
        }


2. Request parameters
 @Controller
        public class SomeController {
            @RequestMapping("/")
            public String redirect() {
                return "redirect:/query?q=Thymeleaf+Is+Great!";
            }
        }
In order to access the q parameter you can use the param. prefix:

    <p th:text="${param.q}">Test</p>


3. Session attributes
-  using #session, that gives you direct access to the javax.servlet.http.HttpSession object: ${#session.getAttribute('mySessionAttribute')}

4. ServletContext attributes
> The ServletContext attributes are shared between requests and sessions

5. Spring beans
- Thymeleaf allows accessing beans registered at the Spring Application Context with the @beanName syntax, for example:

    <div th:text="${@urlService.getApplicationUrl()}">...</div> 


