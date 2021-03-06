# API


SpringBoot application
 - Performance
 - Scalability
 - Caching mechanism
 - Compress payload when sending request (gzip)
 - Maintainability


Spring Boot Concurrency Basics: 

Maximum number of threads – This is the maximum number of threads that are allocated for dealing with requests to the application
	Use the property server.tomcat.max-threads to control how many threads you want to allow. 
	This is set to 0 by default which means- use the Tomcat default which is 200

Shared external resources – Calls to external shared resources such as databases

Asynchronous method calls – These are method calls that release the thread back to the thread-pool when waiting for a response
	https://spring.io/guides/gs/async-method/

Shared internal resources – Calls to internal shared resources- such as caches and potentially shared application state

https://www.e4developer.com/2018/03/30/introduction-to-concurrency-in-spring-boot/


Spring Boot best practices
    Use Auto-configuration
    Use Spring Initializr for starting new Spring Boot projects
    Consider creating your own auto-configuration for common organizational concerns
    Structure your code correctly
    Keep your @Controller’s clean and focused
        Controllers should be stateless! Controllers are by default singletons and giving them any state can cause massive issues.
        Controllers should not execute business logic but rely on delegation.
        Controllers should deal with the HTTP layer of the application. This should not be passed down to Services.
        Controllers should be oriented around a use-case / business-capability.
    Build your @Service’s around business capabilities
    Keep your business logic free of Spring Boot code
    Favour Constructor Injection
    Be familiar with the concurrency model
    Externalise and mature your configuration management
        Use a configuration server, something like Spring Cloud Config
        Store all your configuration in environment variables (that could be provisioned based on git repository)
    Provide global exception handling
        https://www.baeldung.com/exception-handling-for-rest-with-spring
    Use a logging framework
    Use testing slices to make your testing easier and more focused
        https://spring.io/blog/2016/08/30/custom-test-slice-with-spring-boot-1-4

Clean Architecture with Uncle Bob
https://www.e4developer.com/2018/07/14/discovering-clean-architecture-with-uncle-bob/


