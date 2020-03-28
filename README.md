# mnModbus：一个Modbus协议栈

Modbus作为开放式的工业通讯协议，在各种工业设备中应用极其广泛。本人也使用Modbus通讯很多年了，或者用现成的，或者针对具体应用开发，一直以来都想要开发一个比较通用的协议栈能在后续的项目中复用，而不必每次都写一遍。现在利用项目研发的机会，开发一个自己的Modbus协议栈。

## 1、基本功能
首先，本软件是一个协议栈，支持RTU主站、RTU从站、ASCII主站、ASCII从站、TCP客户端和TCP服务器的Modbus通讯。到目前为止本软件支持的功能码如下：
- 0x01功能码，读线圈——对可读写型的状态量进行读取
- 0x02功能码，读输入状态——对只读型的状态量进行读取
- 0x03功能码，读保持寄存器——对可读写型的寄存器量进行读取
- 0x04功能码，读输入寄存器——对只读型的寄存器量进行读取
- 0x05功能码，写单个线圈——对单个的读写型的状态量进行写入
- 0x06功能码，写单个寄存器——对单个的读写型的寄存器量进行写入
- 0x0F功能码，写多个线圈——对多个的读写型的状态量进行写入
- 0x10功能码，写多个寄存器——对多个的读写型的寄存器量进行写入

Modbus协议是一种主从（或者说客户端/服务器）模式协议，由主站（客户端）发起事务请求，从站（服务器）响应事务请求。

## 2、如何使用

本软件封装了Modbus协议栈及RTU主站、RTU从站、ASCII主站、ASCII从站、TCP客户端和TCP服务器6类对象，根据自己的需要直接使用这6类对象就可方便的实现响应的功能。关于个函数及对象的说明可以查看《Modbus协议栈编程手册》文档。

## 3、多主站支持

本次更新添加的在串行链路和以太网链路上多主站站支持。在同一台设备上可以实现多个主站，方便如联网服务器、协议转换器的需求。各个主站相互独立，数据更新回调函数可单独编写，也可以公用。根据使用的数据量自行决定。

## 4、说明
本套协议栈完全开源，任何人都可以使用和修改！同时欢迎交流和浏览我们的博客：
- CSDN：https://blog.csdn.net/foxclever
- 博客园：https://www.cnblogs.com/foxclever/
- 同时欢迎关注我们的微信公众号：“木南创智”
!.[公众号].(https://github.com/foxclever/ExPeriphDriver/blob/master/pic/gzh.png)
