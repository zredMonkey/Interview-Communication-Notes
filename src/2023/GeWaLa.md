### 1. springboot怎么实现热部署？(==没回答上来，框架实现热部署的问题一下子懵逼了==)
答：
在pom.xml文件里添加开发工具依赖
```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
</dependency>

```
然后再在idea里配置，
单击[file]->[settings]菜单项，打开设置对话框，找到complier，勾选择build project automatically （自动构建项目）。

[链接](https://blog.csdn.net/m0_62617719/article/details/130824260)

### 2. 用redis实现消息队列(==只说了用列表的数据类型，具体细节没说==)
答：
Redis实现消息队列的思路是使用列表的插入和取值特性，结合Redis的插入值特性，使用rpop和rpush命令来实现消息队列。但是，使用rpop和rpush命令会消耗大量资源，且出队时需要轮询消息队列，不太合理。因此，Redis中可以使用阻塞式读取命令BRPOP，当消息队列是空时会阻塞等待，当消息队列有后会重新出队。
[链接](https://blog.csdn.net/xueyu188/article/details/131511746)

### 3. 分布式锁有哪些缺陷 (==想错了，想成redisson实现分布式锁，它解决了锁续期等缺陷问题，面试官应该问的是redis实现的==)
答：
- 非原子操作（setnx + expire）
- 被别的客户端请求覆盖（ setnx + value为过期时间）
- 忘记设置过期时间
- 业务处理完，忘记释放锁
- B的锁被A给释放了
- 释放锁时，不是原子性
- 锁过期释放，业务没执行完
- Redis分布式锁和@transactional一起使用失效
- 锁可重入
- Redis主从复制导致的坑

[链接](https://baijiahao.baidu.com/s?id=1764407142914874636&wfr=spider&for=pc)

### 4. mybatis的一二级缓存(==不了解，没答上来==)
[链接](https://baijiahao.baidu.com/s?id=1611406318430829560&wfr=spider&for=pc)

### 5. dubbo的底层协议(==回答了项目中dubbo的通信协议用的是dubbo，默认的，没改，面试官复述了一遍问题，没理解，就没答==)
答：
[链接](https://blog.csdn.net/weixin_53742691/article/details/131906253)

### 6. 算法：有6、7、8、9这4个数字,能组成多少个互不相同且无重复数字的三位数(==想复杂了==)
要用Java实现这个问题，你可以使用嵌套的循环来生成所有可能的三位数，并在生成过程中排除重复的数字。以下是一个简单的Java程序，实现了这个算法：

```java
public class ThreeDigitNumbers {
    public static void main(String[] args) {
        int count = 0; // 用于计数符合条件的三位数的个数

        // 嵌套循环生成所有可能的三位数
        for (int i = 6; i <= 9; i++) { // 百位数循环
            for (int j = 6; j <= 9; j++) { // 十位数循环
                for (int k = 6; k <= 9; k++) { // 个位数循环
                    // 检查是否三个数字互不相同
                    if (i != j && i != k && j != k) {
                        int number = i * 100 + j * 10 + k; // 构造三位数
                        System.out.println(number); // 打印符合条件的三位数
                        count++;
                    }
                }
            }
        }

        System.out.println("共有 " + count + " 个符合条件的三位数。");
    }
}
```

这个程序使用了三个嵌套的循环来生成所有可能的三位数。在循环中，它检查是否三个数字互不相同，并将符合条件的三位数打印出来。最后，它会统计并输出符合条件的三位数的总数。

算法思想是通过穷举所有可能的组合来解决问题，并在生成过程中排除重复的数字。这种方法通常称为"穷举法"，在这个问题中，穷举了所有可能的百位、十位和个位数字的组合，然后检查它们是否互不相同。这是一种基本的解决方法，适用于小规模的问题。



