## 项目：
### 1.做过的项目提问(==非常详细非常详细==)

## 八股文：
### 2.mysql的主从复制
答：
MySQL的主从复制（Master-Slave Replication）是一种数据复制机制，它允许将一个MySQL数据库（主库）的数据复制到其他一个或多个MySQL数据库（从库）上。主从复制常用于实现数据备份、负载均衡和高可用性等需求。

以下是MySQL主从复制的基本工作原理和流程：

1. **主库（Master）：** 主库是数据复制的源头，它负责接收和处理写操作（INSERT、UPDATE、DELETE）并记录到binlog（二进制日志）中。binlog是主库用来记录数据库更改操作的日志文件。

2. **从库（Slave）：** 从库是数据复制的目标，它连接到主库并通过读取主库的binlog来复制数据变更操作。从库会将主库的数据更改操作逐一执行，从而保持与主库数据一致。

3. **复制过程：** 主库将写操作记录到binlog中，从库通过一个I/O线程连接到主库，并实时读取binlog中的数据变更操作。从库将这些操作记录到自己的中继日志（relay log）中。

4. **执行过程：** 从库通过一个SQL线程从中继日志中读取数据变更操作，并在本地执行这些操作，以便在从库上复制主库的数据变更。从库执行这些操作的顺序与主库上写入操作的顺序一致，确保数据的一致性。

5. **延迟和并行复制：** 从库的复制过程可能会有一定的延迟，因为需要等待主库的binlog生成并传输。为了减少延迟，MySQL支持并行复制，即从库可以同时连接多个主库线程，从多个主库复制数据。

6. **故障处理：** 如果主库发生故障，可以手动切换到从库作为新的主库，从而实现高可用性。一旦主库恢复，可以将它重新设置为新的从库，继续参与数据复制。

需要注意的是，MySQL主从复制是一个异步过程，从库的数据可能不会立即与主库保持完全一致。在某些情况下，可能会出现复制延迟或数据不一致的情况，因此在设计和使用主从复制时需要考虑这些因素，并采取适当的监控和管理措施。

### 3.还有一些问题，忘记了







项目假设场景解决方案没怎么想出来，八股文有些没答上来，挂。