# Java Spring interview question

### Q1: What is Spring framework?
> Difficulty : ⭐

It is a lightweight, loosely coupled and integrated framework for developing enterprise applications in java.

### Q2: What is the used of Spring framework?
> Difficulty : ⭐

Spring Framework is extensively used for:

- Web Application Development

- RESTful Web Services

- Securing Web Applications

- Interaction with DataBase

- Testing Purposes

- Used for Standalone Projects

- Integrate Social Media Login (OAuth)

### Q3: What is Dependency Injection?
> Difficulty : ⭐⭐

**Dependency Injection (DI)** is a technique that makes a class independent of its dependencies. It achieves that by decoupling the usage of an object from its creation. 

### Q4: What is Inversion of Control (IOC)?
> Difficulty : ⭐⭐

**IOC** is a principle all about inverting the control of program which the control of objects or portions of a program is transferred to a container or framework. Mostly used in context of OOPs programming.

### Q5: What are some advantages of using Dependency Injection(DI)?
> Difficulty : ⭐⭐

- Loosely couple architecture.
- It is more reusable, more testable, more readable code.
- Testing can be performed using mock objects.
- Increased module reusability.
- ...

### Q6: What is Tight Coupling?
> Difficulty : ⭐⭐

When a class (ClassA) is dependent on another class’s object (ClassB), then we say ClassA is "tightly" Coupled with ClassB. Spring helps us to create classes in a way that Tight Coupling can be removed and Loose Coupling can be done.

### Q7: What is Loose Coupling?
> Difficulty : ⭐⭐

Loose Coupling removes the dependency of an object (ClassB) on a class (ClassA). Loose Coupling is approached by creating an interface and a setter & getter method, or by using a constructor which takes the interface object. 

### Q8: What are Beans in Spring?
> Difficulty : ⭐⭐

When a class is annotated or decorated using the @Component, such a class is called a Bean in Spring. Beans are maintained by Application Context.

### Q9: Types of IOC in Spring?
> Difficulty : ⭐⭐⭐

There're 2 types of IOC in Spring:
- BeanFactory
- ApplicationContext

### Q10: What are differences of `ApplicationContext` over `BeanFactory`?
> Difficulty : ⭐⭐⭐

`ApplicationContext` includes all functionality of the `BeanFactory`, it is generally recommended that it be used in preference to the `BeanFactory` [Base on the Sptring framework docs](https://docs.spring.io/spring/docs/2.5.x/reference/beans.html#context-introduction-ctx-vs-beanfactory).

`BeanFactory` is the basic container whereas `ApplicationContext` is the advanced container. `ApplicationContext` extends the `BeanFactory` interface. It provides more facilities than `BeanFactory` such as integration with spring AOP, message resource handling for i18n, etc...

### Q11: How to create `ApplicationContext` in Spring?
> Difficulty : ⭐⭐⭐

There are 2 ways to create `ApplicationContext` in Spring framework:

**1. By XML file**:
- `FileSystemXmlApplicationContext`: Here you need to provide the full path of the XML bean configuration file.
- `ClassPathXmlApplicationContext`: Here you do not need to provide the full path of the XML file but you need to set CLASSPATH properly.

**2. By using config class with `@Configuration` annotation**:
- Using `AnnotationConfigApplicationContext` implementation to read the config file.

### Q12: What is autowiring in spring?
> Difficulty : ⭐⭐⭐

Autowiring enables the programmer to inject the bean automatically. We don't need to write explicit injection logic. For example:

- Create Bean with XML file:

```XML
<bean id="user" class="com.jimmy.User" />  
```

- Create Bean with annotation:

```java
@Component
class User {

}
```

### Q13: Explains types of Dependency Injection(DI) in Spring?
> Difficulty : ⭐⭐⭐⭐

There're 2 types of DI in Spring framework. For example we using these class:

```java
class Address {
    private String location;

    // Getter and setter method...
}

class User {
    private String email;
    private String username;
    private Address address;

    public User (Address address){
        this.address = address;
    }
}
```
**1. Constructor DI**:

Create DI using XML:
```XML
<bean id="address" class="com.jimmy.Address" />  

<bean id="user" class="com.jimmy.Address">
    <constructor-args ref="address"/>
</bean>
```

Create DI using annotations:
```java
@Autowired
class Address {
    private String location;

    // Getter and setter method...
}

class User {
    @Autowired
    private Address address;

    public User (Address address){
        this.address = address;
    }
}
```
**2. Properties DI**:

Properties file:

```
foo.email=jim.dangquoc706@gmail.com
foo.username=dungdeptrai
```
Create DI using XML:
```XML
<!-- load the properties file:  -->
<context:property-placeholder location="classpath:application.properties"/>
<bean id="address" class="com.jimmy.Address" />  

<bean id="user" class="com.jimmy.Address">
    <property name="address" ref="address"></property>
</bean>
```

Create DI using annotation:
```java
@Autowired
class Address {
    private String location;

    // Getter and setter method...
}

class User {
    @Autowired
    private Address address;

    @Value("${foo.email}")
    private String email;
    @Value("${foo.username}")
    private String username;

    public User (Address address){
        this.address = address;
    }
}
```

### Q14: Explain Bean creation process?
> Difficulty : ⭐⭐⭐

The process of Bean creation has the following phases:

1. Starts with a class (c1) which has the annotation @Component.
2. Checks if the component annotated class (c1) is dependent.
3. If yes, then Spring will create a bean for that class (c2) too.
4. A connection or autowiring will occur between the two classes (c1 and c2) using `@Autowired` annotation and also through the constructor (c2) 

### Q15: What are differences types of Spring Bean scopes?
> Difficulty : ⭐⭐⭐

**1.Singleton**: The bean instance will be only once and same instance will be returned by the IOC container. It is the default scope.

**2. Prototype**: The bean instance will be created each time when requested.

**3. Request**: The bean instance will be created per HTTP request.

**4. Session**: The bean instance will be created per HTTP session.

### Q16: Differentiate `@Component, @Repository, @Service,  @Controller`?
> Difficulty : ⭐⭐⭐

Typically a web application is developed in layers like the controller (which is the initial point of client communication), business (where the actual code or logic of the application is written) and DAO (where the database connections and interaction happens). In such an architecture web application, `@Component` can be used in any of the layers. Whereas, the `@Controller` is used in the controller/web layer. `@Service` is used in the business layer and `@Repository` is used in the DAO layer.

### Q17: What is a FrontController?
> Difficulty : ⭐⭐⭐

A Front Controller is a common pattern in web application and used to receive request and delegate to other components in the application for actual processing. 

### Q18: What is a ViewResolver?
> Difficulty : ⭐⭐

**ViewResolver** enables a web application to select its view (such as JSP) dynamically. ViewResolver gets a name which is appended by /WEB-INF/views and a .jsp. All the display on the content is done in an HTML page. You can create ViewResolver with `InternalResourceViewResolver` class.

### Q19: List out all the concepts that are available in the MVC Architecture?
> Difficulty : ⭐⭐⭐

1. The Browser sends a request to **DispatcherServlet**.
2. **DispatcherServlet** know and can find the appropriate controllers for the request.
3. Controllers execute the request and put the data in the model and return back the view name to the **DispatcherServlet**.
4. **DispatcherServlet** uses the view name and **ViewResolver** to map to the view.

### Q20: List the steps to create config in Spring Hibernate?
> Difficulty : ⭐⭐⭐

1. Create a Bean implementation of DataSource with `ComboPooledDataSource` class.
```java
ComboPooledDataSource myDataSource = new ComboPooledDataSource();
```
2. Setting up the URL, User and Password for jdbc:
```java
myDataSource.setJdbcUrl("url");
myDataSource.setUser("username");
myDataSource.setPassword("password");
```
3. Setting up the connection pools
```java
myDataSource.setInitialPoolSize("initialPoolSize");
myDataSource.setMinPoolSize("minPoolSize");
myDataSource.setMaxPoolSize("maxPoolSize");		
myDataSource.setMaxIdleTime("maxIdleTime");
```
4. Create a Bean for SessionFactory with `LocalSessionFactoryBean` class.

### Q21: What are the advantages of JdbcTemplate in spring?
> Difficulty : ⭐⭐⭐

By using the JdbcTemplate class, you don't need to create connection,statement,start transaction,commit transaction and close connection to execute different queries. You can execute the query directly.

### Q22: Define `@ControllerAdvice`?
> Difficulty : ⭐⭐⭐

This annotation will run AFTER controllers class and it base on AOP aspect. Usally used with `@ExceptionHandler` annotation for handle errors.

### Q23: What is AOP?
> Difficulty : ⭐⭐⭐⭐

AOP is an acronym for Aspect Oriented Programming. It is a methodology that divides the program logic into pieces or parts or concerns.

It increases the modularity and the key unit is Aspect.

### Q24: What is the advantages of AOP?
> Difficulty : ⭐⭐⭐⭐

1. Enable add or remove concern before or after bussiness logic.
2. Configuable.
3. Code for Aspect defined in a single class -> easier for maintance.
4. Reduce code complexity.

### Q25: Use cases of AOP?
> Difficulty : ⭐⭐⭐⭐

- Logging, security
- Data transactions
- Exceptions handle
- ...

### Q26: List AOP terminology?
> Difficulty : ⭐⭐⭐⭐⭐

- **Aspect**: a module of code for a cross-cutting concern (logging, transcation...). In Spring Aspect can be implemented by using `@Aspect` annotation.
- **Advice**: What action be taken and when should be applied
- **Join Point**: When to applied code during program execution. For example:  field access, method execution, exception handling etc... (Spring only support method execution Join Point only)
- **Point Cut**: a predicate that matches join points.
- **Weaving**: Connecting Aspect to target object and create an advised object. This can be done at compile time (using the AspectJ compiler, for example), load time, or at runtime. Spring AOP, like other pure Java AOP frameworks, performs weaving at runtime.

Advice, Join Point, Point Cut example:
![AOP](./img/aop.png "AOP")

### Q27: What are the types of advice in AOP?
> Difficulty : ⭐⭐⭐⭐

There are 5 types of advices in spring AOP.

1. **Before Advice**: Run before the method
2. **After Advice**: Run after the method (finally in try-catch for example)
3. **After Returning Advice**: Run after the method successfully executed
4. **Throws Advice**: Run after method throwing exception
5. **Around Advice**: Run BEFORE and AFTER method

