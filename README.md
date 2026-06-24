# LD2460-STM32F4-HAL
基于海陵科LD2460雷达进行人体探测，实现人体跟踪或导盲提醒


本程序采用STM32F407VET6基于LD2460进行开发

（1）将源码中的Transmit.c和Transmit.h文件导入工程中
（2）配置CubeMX : 开启两个串口，USART1用于单片机与LD2460通信，USART2用于上位机测试或接下来与其他模块通信
 (3)在主函数中导入Transmit.h头文件，声明两个变量UART_HandleTypeDef huart1、RadarInfo_t radar_info;
（4）在main中调用初始化函数Radar_UART_Init()；
（5）在while循环中Radar_Scan_Frame()循环扫描接收数据


注：1.上位机串口的重定向
2.LD2460表面上的两个芯片的方向（与板子垂直方向）为Y轴正方向，具体可查看官方文档 https://h.hlktech.com/Mobile/download/FDetail/349.html
