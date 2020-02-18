<<<<<<< HEAD
# -
command line interface 、python
=======
```系统存储的数据放在:data.txt

存放条目有:1. 车牌号(六个字符）、 2.卡类（2：年卡；1：次卡；0：临时卡）、3.进场时间（年月日时分秒xx-xx-xx-xx-xx-xx）
         4. 出场时间(12个字符型数字, 格式同进场时间)
         5. 针对教职工还要保存六位工号、
         6. 年卡用户：卡到期时间
            次卡用户：卡剩余次数

```完整的一条记录如下:
A66666 2 200124140329 200124150423 458135 200918


功能要求:
(1) 信息读取：从文件（如car.txt）中将所有信息读入程序

(2) 添加记录：主要用于员工办卡。从键盘读入完整信息，如果员工在系统中不
             存在，则在数组中增加一条记录；如果员工已存在，且名下有一台车，
             则在数组中增加一条记录；如果员工已存在，且名下有两台车，
             则给出提示，不添加。

(3) 浏览记录：显示数组中所有记录的信息

(4) 车辆进场：从键盘读入车牌信息和入场时间；检索数组，如果该车已存在，
            并且未进场，则将入场时间写入该条记录；如果该车不存在，则
            创建记录，类型为临时卡，将入场时间写入该条记录。

(5) 车辆出场：从键盘读入车牌信息，出场时间；检索数组，如果该车已存在，
            则根据门卡类型、停车时长、单价计算并输出需缴费用，并写入
            出场时间；如果该车不存在，则给出提示。

(6) 计费标准：年卡用户且另一台车不在校园：在有效期内收费为0；
             次卡用户且另一台车不在校园：如果剩余次数不为0则剩余次数
             减1；临时卡用户或者固定卡用户但是另一台车已在校园：第一
             小时5元，之后每小时3元，不足一小时按一小时计算。

(7) 修改记录：首先查找需要修改的记录，再修改其中的一个或者多个字段的值

(8)  数据排序：输入字段名称，对数组中所有记录，按照所选字段排序

(9)  数据保存：将数组中的所有信息写回文本文件car.txt中

(10) 退出：退出系统。


///注意///:   员工办理年卡或者次卡时，每位员工只能办理一张卡，每张卡最多可以用于两台车，
             同一时间属于同一员工的车辆如果有多于一台在校园里，
             则只有最先进入校园的一台按照固定卡扣费，另一台需要按照临时卡管理。

本程序作如下约定：1. 车辆进场后,除了修改修改进场时间，还要把上一次的出场时间清空。
                   代表车现在在停车场里面。出场时，不做任何修改。

                  2.  办卡时只是填入基本信息，不对车辆进场。即新办的卡，进场出场时间
                    都为 "xxxxxxxxxxxx"

                  3.  车库里每个条目里的进出场信息，无非以下四种状态:
		      (其实只有三种,用1表示该处有信息,用x表示该处无信息)
                    （1） x x --> 刚办完卡：可以进场，但不能出场
                    （2） x 0 --> 不存在。
                    （3） 0 x --> 刚进完场的状态:不可以进场，但可以出场
                    （4） 0 0 --> 刚出完场的状态:可以进场，但不能出场

              	  4. 当剩余次数为0时，或是年卡用户到期：只是给予冻结警告，后续逻辑没有写。

                  5. 当剩余次数不足5次时，或者到期时间不足一个星期，给予友好提醒.

>>>>>>> 第一次提交
