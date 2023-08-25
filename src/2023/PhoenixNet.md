2023-6 凤凰网面试

一、项目
问了很多

二、八股文
**1.SpringBoot和Spring比有什么优点？**
答：
Spring Boot 和传统的 Spring 框架有许多优点，它们使得开发更加方便、快速和高效。以下是 Spring Boot 相对于传统 Spring 框架的一些优点：

1. **简化配置：** Spring Boot 提供了自动配置（Auto-Configuration）机制，能够根据项目的依赖自动配置应用程序。这消除了繁琐的XML配置，减少了配置文件的编写工作，加快了开发速度。

2. **快速启动：** Spring Boot 提供了嵌入式的 Web 服务器，如Tomcat、Jetty等，无需手动部署，可以快速启动应用程序进行开发和测试。

3. **自带依赖管理：** Spring Boot 管理了一组常用的第三方依赖，这些依赖的版本被预先定义和配置，减少了依赖冲突和版本问题。

4. **生产就绪特性：** Spring Boot 提供了各种监控、度量、健康检查、安全等功能，可以更方便地将应用程序部署到生产环境。

5. **注解驱动：** Spring Boot 鼓励使用注解来配置和管理组件，使得代码更加简洁可读，而不是通过繁琐的XML配置。

6. **开箱即用：** Spring Boot 提供了许多开箱即用的特性，如热部署、自动刷新、自动重启等，简化了开发过程中的开发、测试和调试。

7. **微服务支持：** Spring Boot 是构建微服务架构的理想选择，它提供了诸多支持微服务的特性，如服务注册、发现、追踪等。

8. **集成Spring生态：** Spring Boot 不仅支持 Spring 框架的核心功能，还集成了许多 Spring 生态的项目，如Spring Data、Spring Security、Spring Cloud等，便于快速构建复杂应用。

9. **社区支持：** Spring Boot 拥有活跃的开发社区，有大量的文档、示例和教程，使开发者能够快速上手和解决问题。

总体来说，Spring Boot 在简化开发、提高效率、降低学习曲线等方面具有明显的优势，特别适合构建现代化的应用程序，尤其是微服务架构。然而，具体选择使用 Spring Boot 还是传统的 Spring 框架，取决于项目需求、开发团队的技能和偏好。

**2.SpringBoot怎么实现自动配置的？**
答：
Spring Boot 实现自动配置的核心机制是通过条件注解（`@Conditional`）和组件扫描来实现的。以下是 Spring Boot 自动配置的主要步骤：

1. **条件注解（`@Conditional`）：** Spring Boot 使用条件注解来控制是否应用特定的自动配置。这些条件注解基于运行时的条件判断，如果满足条件，则相应的自动配置将被激活。

2. **自动配置类（`@Configuration`）：** Spring Boot 的自动配置是通过在类上添加 `@Configuration` 注解的配置类来实现的。这些自动配置类中定义了各种组件的配置信息，如数据源、Web服务器、消息队列等。

3. **自动配置条件判断：** 在自动配置类中，通过条件注解对是否应用该自动配置进行判断。条件注解的逻辑是基于一些条件接口的实现类，这些条件接口可以根据运行时环境和配置属性进行判断。

4. **组件扫描：** Spring Boot 会自动扫描项目中的 `META-INF/spring.factories` 文件，该文件中列出了所有自动配置类的全限定类名。这些自动配置类将会被自动加载并应用。

5. **配置属性绑定：** Spring Boot 使用配置属性绑定机制，将外部配置文件中的属性值绑定到自动配置类中的属性上。通过 `@ConfigurationProperties` 注解来实现属性的绑定。

6. **优先级：** 自动配置的优先级是根据条件的复杂性和源头的不同而定的。例如，项目中显式定义的配置会覆盖自动配置中的默认值。

通过这些步骤，Spring Boot 实现了自动配置，使开发者能够在不显式进行繁琐配置的情况下，轻松地集成和使用各种组件和功能。自动配置使得项目的构建、测试和部署更加简单，减少了开发工作量，同时也保证了项目的一致性和稳定性。

**3.说说Tomcat。**
答：
Apache Tomcat（简称Tomcat）是一个开源的Java Servlet容器，也可以作为Web服务器使用。它是由Apache软件基金会开发和维护的，是一个流行的Java应用程序服务器，用于运行Java Servlet和JavaServer Pages（JSP）等Web应用程序。

以下是Tomcat的一些主要特点和功能：

1. **Servlet容器：** Tomcat作为Servlet容器，可以处理Java Servlet和JSP等Web组件，为Java Web应用提供运行环境。

2. **独立运行：** Tomcat可以作为一个独立的Web服务器运行，也可以作为其他Web服务器（如Apache HTTP Server）的Servlet容器来使用。

3. **嵌入式支持：** Tomcat支持嵌入式模式，可以嵌入到Java应用程序中，使得应用程序能够自包含地运行Servlet容器。

4. **支持标准：** Tomcat遵循Java Servlet和JSP的相关标准，如Java Servlet规范、JavaServer Pages规范等，确保了Web应用的兼容性。

5. **虚拟主机：** Tomcat支持虚拟主机，可以在同一服务器上运行多个域名或多个Web应用，实现资源的隔离和共享。

6. **连接器：** Tomcat支持多种连接器，如HTTP连接器、AJP连接器等，可以处理不同协议的请求。

7. **管理界面：** Tomcat提供了Web管理界面，可以通过浏览器访问，管理和监控Web应用、连接池、内存使用等。

8. **安全性：** Tomcat提供了安全机制，支持SSL/TLS加密、访问控制等，保护Web应用的安全性。

9. **扩展性：** Tomcat支持扩展，可以通过添加插件和组件来增强功能，如数据源连接池、集群支持等。

10. **社区支持：** Tomcat拥有活跃的开发和用户社区，提供丰富的文档、示例和支持，使开发者能够更好地使用和维护Tomcat。

总体来说，Apache Tomcat是一个稳定、可靠且功能丰富的Java Servlet容器和Web服务器，适用于运行各种规模的Java Web应用程序。它被广泛应用于生产环境中，支持Java开发者构建和部署高性能的Web应用。

**4. Tomcat怎么辨别jar包和war包？** ==【！！！没回答上来】==
答：
在Tomcat运行应用程序时，通常需要辨别是使用Jar包还是War包进行部署。下面解释了这两种部署方式的区别以及如何辨别它们：

**WAR包（Web Application Archive）：**

WAR包是一种用于打包和部署Java Web应用程序的压缩文件格式。它包含了Web应用程序的所有资源，包括Servlet类、JSP文件、HTML、CSS、JavaScript、配置文件等。WAR包的部署方式适用于Java Web应用，可以将整个Web应用程序打包为一个独立的WAR文件，然后部署到Tomcat中。

辨别WAR包的特征：
- 文件后缀为 `.war`。
- 包含了Web应用程序的所有资源。
- 在Tomcat的`webapps`目录下，将WAR文件放置到该目录下，Tomcat会自动解压并部署。

**JAR包（Java Archive）：**

JAR包是一种用于打包Java类、资源文件等的压缩文件格式。JAR包通常用于打包独立的Java应用程序或Java库。在Web应用的上下文中，JAR包可以用于包含一些Java类库，但它不是直接用于部署整个Web应用的。

辨别JAR包的特征：
- 文件后缀为 `.jar`。
- 通常包含Java类、资源文件等。
- 不适用于直接部署Java Web应用。

通常情况下，当您希望将整个Java Web应用程序部署到Tomcat中时，您应该选择WAR包方式。而当您只想引入一些Java类库或资源文件时，可以选择使用JAR包方式。在部署到Tomcat时，务必将WAR包放置到Tomcat的`webapps`目录下，以便Tomcat能够正确解析和部署您的应用程序。

**5. 多线程用的多吗？**

**6. 项目的QPS是多少？**

三、算法题 ==【！！！用栈实现了，但是空间复杂度有点大】==

给定单链表的头节点 head ，请反转链表，并返回反转后的链表的头节点。
输入：head = [1,2,3,4,5]
输出：[5,4,3,2,1]

输入：head = [1,2]
输出：[2,1]

输入：head = []
输出：[]


```
public class ReverseList {

    class ListNode {
        int val;
        ListNode next;
        ListNode(int val) {
            this.val = val;
        }
    }

    public ListNode reverseList(ListNode head) {
        // 初始化前一个节点为 null，当前节点为 head
        ListNode prev = null;
        ListNode current = head;

        // 迭代遍历链表
        while (current != null) {
            // 保存当前节点的下一个节点
            ListNode nextTemp = current.next;

            // 反转指针，将当前节点的下一个节点指向前一个节点
            current.next = prev;

            // 更新前一个节点和当前节点
            prev = current;
            current = nextTemp;
        }

        // 返回新的头节点，即原链表的最后一个节点
        return prev;
    }

}
```



全是Tomcat八股文，没回答上来，算法写出来了，到那时空间复杂度太大，用的是栈解决，但是用迭代最好，空空复杂度可以是o(1)，挂。



