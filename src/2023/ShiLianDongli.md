## 1.问项目

## 2.SpringBoot怎么实现类的自动注入？ (==没回答上来==)
答：

在Spring Boot中，类的自动注入是通过 Spring 框架的自动装配机制来实现的。Spring Boot使用了@ComponentScan注解和@Autowired注解来实现自动注入。

以下是实现类的自动注入的步骤：

1. **创建 Spring Boot 项目：** 首先，你需要创建一个基于 Spring Boot 的项目，可以使用 Spring Initializr 进行快速初始化。

2. **定义需要自动注入的类：** 在你的项目中，创建一个类，比如 `MyService`，并在该类上加上 `@Service` 或其他合适的注解，标识这是一个需要被 Spring 管理的服务类。

   ```java
   import org.springframework.stereotype.Service;
   
   @Service
   public class MyService {
       // ...
   }
   ```

3. **启用组件扫描：** 在 Spring Boot 主应用程序类上加上 `@SpringBootApplication` 注解，它隐式地启用了组件扫描，允许 Spring 自动发现和注册被注解标记的组件。

   ```java
   import org.springframework.boot.SpringApplication;
   import org.springframework.boot.autoconfigure.SpringBootApplication;
   
   @SpringBootApplication
   public class MyApplication {
       public static void main(String[] args) {
           SpringApplication.run(MyApplication.class, args);
       }
   }
   ```

4. **进行自动注入：** 在需要使用 `MyService` 的地方，可以使用 `@Autowired` 注解来进行自动注入。

   ```java
   import org.springframework.beans.factory.annotation.Autowired;
   import org.springframework.stereotype.Controller;
   
   @Controller
   public class MyController {
       
       private final MyService myService;
       
       @Autowired
       public MyController(MyService myService) {
           this.myService = myService;
       }
       
       // ...
   }
   ```

通过以上步骤，Spring Boot 将会自动扫描并发现被标注的组件，并将其注册到 Spring 容器中。当需要注入这些组件时，可以使用 `@Autowired` 注解来实现自动注入，无需手动创建实例。这样可以简化开发过程，提高代码的可维护性和可读性。


## 3.Dubbo的消费消费者怎么调用提供者的？(==没怎么回答上来==)
答：

在 Dubbo 中，消费者（Consumer）通过 Dubbo 的远程调用机制来调用提供者（Provider）的服务。这个过程涉及到注册中心、负载均衡、网络通信等多个步骤。下面是消费者调用提供者的基本步骤：

1. **注册中心：** 首先，消费者和提供者都需要将自己的信息注册到相同的注册中心（如 ZooKeeper、Nacos 等）。注册中心用于管理服务的元数据，包括服务提供者的地址和消费者的信息。

2. **消费者引用服务：** 消费者通过 Dubbo 的配置来引用需要的服务。这通常是通过配置一个 Java 接口，该接口定义了需要调用的远程服务的方法。Dubbo 会自动生成该接口的代理对象，用于远程调用。

3. **负载均衡：** 在多个提供者提供同一服务的情况下，Dubbo 支持多种负载均衡策略，用于在不同的提供者之间分配调用请求。常见的策略有随机、轮询、最少活跃等。

4. **网络通信：** 当消费者调用远程服务的方法时，Dubbo 会根据负载均衡策略选择一个提供者，并通过网络通信发送请求。

5. **提供者处理请求：** 服务提供者接收到请求后，会根据接口定义执行相应的方法逻辑，并返回结果。

6. **返回结果：** 提供者将处理后的结果返回给消费者。

总的来说，Dubbo 的消费者通过引用远程服务接口，Dubbo 在后台负责管理服务的发现、负载均衡、网络通信等细节，使得消费者能够简单地调用远程服务，而不需要关心底层的网络通信和服务查找。这种方式极大地简化了分布式系统中的开发和维护工作。



## 4.dubbo支持哪些协议？(==回答不全==)
**现场回答**：dubbo、http、rest。

答：

Dubbo 支持多种通信协议，用于在服务提供者和消费者之间进行远程调用。以下是 Dubbo 支持的九种通信协议：

1. **Dubbo 协议：** Dubbo 协议是 Dubbo 默认的通信协议，它是一种基于 TCP 的二进制协议，具有较高的性能和效率。适用于内部服务调用，特别适合高性能和低延迟的场景。

2. **RMI 协议：** RMI（Remote Method Invocation）协议是一种 Java 原生的远程调用协议。它允许 Java 客户端和服务端之间的通信，但由于其 Java 特定性，不太适用于跨语言通信。

3. **Hessian 协议：** Hessian 是一种基于 HTTP 的二进制通信协议，具有较好的性能。适用于跨语言通信，特别适合移动端和其他非 Java 平台的消费者。

4. **Http 协议：** Dubbo 也支持基于 HTTP 的通信，可以通过 HTTP 传输 Dubbo 的 RPC 请求和响应。适用于跨网络较长、不同语言之间的通信。

5. **WebService 协议：** Dubbo 支持通过 SOAP 和 XML-RPC 等 WebService 标准协议进行通信。适用于与其他 WebService 标准兼容的系统集成。

6. **Thrift 协议：** Dubbo 也支持 Apache Thrift 协议，它是一种高效的多语言通信协议。适用于不同语言之间的通信。

7. **Memcached 协议：** Dubbo 支持基于 Memcached 协议的通信，适用于缓存服务。

8. **Redis 协议：** Dubbo 也支持基于 Redis 协议的通信，适用于缓存服务。

9. **MongoDB 协议：** Dubbo 支持基于 MongoDB 协议的通信，适用于数据存储和访问。

每种协议都有其适用的场景和优势，Dubbo 的协议灵活性使得开发者可以根据实际需求选择最适合的协议来进行远程调用。



