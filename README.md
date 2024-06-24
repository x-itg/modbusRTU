# Modbus RTU协议

|"/"表示不用|||||||||
|:-------------------------------|:---------:|:---------:|:--------------:|:------------:|:--------------:|:-----------:|:-----------:|:--------:|
|**写入**                        |地址1byte  |功能码1byte|寄存器地址2bytes|寄存器数2bytes|conut字节数1byte| 数据1 2bytes|数据2 2bytes |校验2bytes|
|主机发写多保持型寄存器4字节为例 |115       |0x10       |reg_H reg_L     |reg_H reg_L   | 0x04           |d1_H d1_L    |d2_H d2_L    |CRCH  CRCL|
|从机应答                        |115       |0x10       |reg_H reg_L     |reg_H reg_L   |       /        |    /        |      /      |CRCH  CRCL|
|主机发写单保持型寄存器          |115       |0x06       |reg_H reg_L     |       /      |       /        |d_H     d_L  |      /      |CRCH  CRCL|
|从机应答                        |115       |0x06       |reg_H reg_L     |       /      |       /        |d_H     d_L  |      /      |CRCH  CRCL|
|**读取**                        |地址1byte  |功能码1byte|寄存器地址2bytes|寄存器数2bytes|conut 1byte     |地址/数据    |地址/数据    |校验2bytes|
|主机发读取保持型寄存器          |115       |0x03       |       /        |       /      |     /          |reg_H   reg_L|n_H     n_L  |CRCH  CRCL|
|从机应答 4字节为例              |115       |0x03       |       /        |       /      |  0x04          |d1_H     d1_L|d2_H    d2_L |CRCH  CRCL|
|主机发读取输入型寄存器          |115       |0x04       |       /        |       /      |     /          |reg_H   reg_L|n_H     n_L  |CRCH  CRCL|
|从机应答 4字节为例              |115       |0x04       |       /        |       /      |  0x04          |d1_H     d1_L|d2_H    d2_L |CRCH  CRCL|
-------------------------------------------------------------------------------------------------------------------------------------------------

# stm32cubeide支持sprintf浮点数的打印
- Project->Properties->C/C++ Build->Setting->Tool Setting->勾选 Use float with printf from newlib-nano(-u_printf_float)
<img width="" height="480" class="embed-show" src="http://iamrobot.top:7878/?explorer/share/file&hash=1c41C52ve1ZQbdibwikxXq6kEq9Yry-xGCGfjjthz-elPK8NWsINvoDn8BS4SOrkaxU&name=/3.png" alt="3.png"/>

# 使用stm32cube生成iar和stm32cubeide工程
- 记得**不要勾选**Generate Under Root
<img width="" height="480" class="embed-show" src="http://iamrobot.top:7878/?explorer/share/file&hash=48d4XYjbheDuVVEz4Jll94t7GpHbpWsHO3Ttwv8ZzAXKcKI_nbXljiFe4QRQTYlfjBU&name=/iar%E5%92%8Cstm32cubeide.png" alt="iar和stm32cubeide.png"/>

