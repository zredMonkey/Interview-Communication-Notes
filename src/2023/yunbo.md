### 1.聊项目、聊工作情况

### 2.你觉得RabbitMQ为什么用它？起到了什么作用？(==回答不全==)

答：
在项目中使用 RabbitMQ（或其他消息队列系统）可以带来多个优势，这些优势使得消息队列在构建分布式系统、解耦系统组件、处理异步任务等方面非常有用。以下是一些使用消息队列（如 RabbitMQ）的优势和作用：

1. **解耦系统组件：** 消息队列可以将系统的各个组件解耦，使它们能够独立地进行开发、部署和维护。组件之间通过消息进行通信，而不需要直接调用彼此的方法，从而降低了组件之间的耦合度。

2. **异步通信：** 消息队列允许系统中的不同组件以异步的方式进行通信。这意味着某个组件可以将消息放入队列，而另一个组件可以在合适的时候从队列中取出并处理消息。这有助于提高系统的并发性和响应性。

3. **削峰填谷：** 在高并发情况下，消息队列可以帮助平稳处理流量。例如，一个系统可能在某个时间点会有大量的请求，通过将这些请求放入消息队列中，可以将请求的处理分散到不同的时间段，避免系统崩溃或超负荷。

4. **数据传输：** 消息队列可以用于数据传输和同步。当数据需要从一个系统传递到另一个系统时，可以通过消息队列来确保数据的可靠传输，并提供错误处理机制。

5. **任务调度：** 消息队列可以用于任务调度和异步处理。例如，将异步任务放入队列，然后后台的工作线程可以按顺序处理这些任务，从而避免阻塞主线程。

6. **发布/订阅模式：** 消息队列通常支持发布/订阅模式，允许一个或多个订阅者订阅感兴趣的消息。这对于实现事件通知和日志记录等功能很有帮助。

7. **可靠性和持久性：** 消息队列通常提供可靠性保证，确保消息在发送和接收过程中不会丢失。一些消息队列还支持消息的持久性存储，即使在系统故障时也能保留消息。

总的来说，消息队列在分布式系统中有很多应用场景，可以帮助解决各种通信、协调和处理的问题。它们提供了一种高效、可靠的通信机制，有助于构建可扩展的应用系统。



### 3.JVM调优工具知道哪些？
Arthas(阿里开源的工具)

### 4.Sql中Having和where的区别？(==回答不全面==)
答：

在SQL中，`HAVING` 和 `WHERE` 是两个不同的关键字，用于过滤查询结果中的行。尽管它们看起来有些相似，但在使用时有一些重要的区别：

1. **使用场景：**
   - `WHERE`：用于在查询结果返回之前，筛选源表中的行。它用于过滤源数据，不涉及聚合函数。
   - `HAVING`：用于在聚合操作（如 `GROUP BY`）之后，筛选聚合结果的行。它用于过滤已经进行聚合操作的结果集。

2. **应用对象：**
   - `WHERE`：应用于表的列，用于筛选行级别的数据。
   - `HAVING`：应用于聚合函数的结果，用于筛选聚合结果级别的数据。

3. **使用位置：**
   - `WHERE`：通常位于 `SELECT` 语句的开始或中间，用于筛选源表中的数据。
   - `HAVING`：通常位于具有聚合函数的 `SELECT` 语句的末尾，用于筛选聚合结果。

4. **使用条件：**
   - `WHERE`：可以使用任何列（包括聚合函数的结果），筛选基于单个行的数据。
   - `HAVING`：仅用于筛选基于聚合函数的数据，例如 `COUNT`、`SUM`、`AVG` 等。

以下是一个示例，说明了 `WHERE` 和 `HAVING` 的不同用法：

```sql
SELECT department, COUNT(*) as employee_count
FROM employees
WHERE salary > 50000
GROUP BY department
HAVING COUNT(*) > 5;
```

在这个示例中，`WHERE` 子句用于筛选源表中 `salary` 大于 50000 的员工，然后根据 `department` 列进行分组。然后，`HAVING` 子句用于筛选出拥有大于 5 名员工的部门。

总结起来，`WHERE` 用于筛选行级数据，而 `HAVING` 用于筛选聚合结果级数据。

**注：**

```
SELECT department, AVG(salary) as avg_salary
FROM employees
WHERE gender = 'Male'
GROUP BY department
HAVING AVG(salary) > 60000
ORDER BY avg_salary DESC;
```
这个示例中的查询选择了男性员工的平均工资超过60000的部门，然后按照平均工资降序排序。

通过合理地使用 WHERE、HAVING和ORDER BY，可以更精确地获取所需的数据，并以所需的方式进行排列。



### 5. 复杂Linux操作有欠缺，找时间补充学习

### 6.还有一堆问题






二面比对无下文了。。。