> H4lo@HatLab

## 某款路由器固件提取步骤

以某一款国内的路由器举例，来从设备硬件中读取固件的方法：

1 . 用螺丝刀卸下螺丝之后，拆开设备的外壳，可以看到 PCB 板内部的情况：

![](./img/5e72c91890502.png)

观察板子结构，在右边的 EtronTech 是一个存储器芯片，也就是 SDRAM 。中间的是联发科的主控芯片。

2 . 左边有印字的八脚芯片就是一个 SPI 封装的 flash rom，厂商名称是 `BoyaMicro`，型号是 `25Q32AS81G`。我们的目标就是从这个 flash 中读出固件内容。

![](./img/5e72e1c03c559.png)

3 . 同样的使用热风枪对准 flash，慢慢将其吹下：


吹下之后拿到 flash：

![](./img/5e7249a03e99a.png)

4 . 接着使用芯片夹和编程器，使用相应的编程器软件对 flash 进行读取：

![](./img/5e72e22bec003.png)

- 这里必须要夹准针脚，否则会出现识别不出来的情况。


### 可能遇到的问题

如果遇到未知芯片型号的问题，则是因为编程器不支持这个芯片的读取，可以换一个支持型号多的编程器。

![](./img/5e72e28d3ea6a.png)

