## 一 RabbitMQ简介
RabbitMQ可以用于实现大并发时的消息队列，同时处理不同的web服务器之间通信需求。  
所谓队列，就是抢占资源时的排队，消息就是不同服务器见传送的数据单位，可以是json、文本等。  
使用消息队列的优势是：
- 1-应用解耦：消息对垒在处理项目需求时，在中间插入了隐含的基于数据的接口层，两边的处理过程都要实现这一接口。这允许你独立的扩展活修改两边的处理过程，只要遵守同样的接口约定即可。
- 2-可扩展性：可以方便的实现大消息入队和处理的频率
- 3-灵活性与峰值处理能力：消息队列可以应对临时的突发高峰值访问
- 4-缓冲提升性能
- 5-异步通信：很多消息不需要立即处理，消息队列可以提供异步处理机制。
RabbitMQ的安装：
```
docker安装：
sudo docker pull rabbitmq
docker run -d -e RABBITMQ_NODENAME=my-rabbit --name some-rabbit -p 5672:5672 rabbitmq:3

mac安装：
    brew install rabbitmq
    vim ~/.bash_profile    //添加： export PATH=$PATH:/usr/local/sbin
    source ~/.bash_profile
    rabbitmq-server       // 重新打开终端输入
    浏览器输入：http://localhost:15672/     //账号密码全输入guest即可登录

    如果显示找不到主机，请在hosts文件中添加:
    vim /private/etc/hosts
    127.0.0.1  localhost

```
