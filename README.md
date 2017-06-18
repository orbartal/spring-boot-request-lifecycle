# spring.boot.request.process.stages
Log all the stages of processing an http request in spring boot. 

After reading and learning about the request lifecycle (processing) in spring MVC
I decided to create a spring boot sample project to test it.
I used log to track the path of a request in Spring MVC. 


Spring Boot default request lifecycle
1. Filters
2. Handler interceptors
3. DispatcherServlet (using HandlerMapping and HandlerAdapter)
4. A servelet that is define by a Spring MVC Controller method 
  (map to by the HandlerMapping, by default according to the values in the  annotation of @contoller and @RequestMapping)
5. The developer define logic: The method in the controller calls a spring service to do something...
   For now we only care about the data the controller return, and the way it return it. 
6. Back to the Handler interceptors in the reverse order (last to first)
7. Back to the filters in the reverse order (last to first)

Not that this is Spring Boot default request lifecycle.
It can all be customized by the developer. 

Data sources:
https://stackoverflow.com/questions/11507477/spring-web-flow-how-is-a-request-handled
https://jakubstas.com/spring-professional-study-notes/#.WUaMx2jytzo 
https://examples.javacodegeeks.com/enterprise-java/spring/mvc/spring-mvc-interceptor-tutorial/
