## 用qemu调试linux内核

*2016-06-16*

参考[五分钟内搭建 Linux 0.11 的实验环境][2]，非常感谢作者！这是我经历的最用心的作品之一！

打开控制台A

    $ sudo yum install qemu
    $ git clone https://github.com/tinyclub/linux-0.11-lab.git
    $ cd linux-0.11-lab && make
    $ make debug-hd

打开控制台B

    $ gdb images/kernel.sym
    (gdb) target remote:1234
    (gdb) b main
    (gdb) c
    (gdb) l

### 参考资料

* [《Linux内核完全注释》][1]：大学时拜读过，对内核的学习帮助非常大。

* [五分钟内搭建 Linux 0.11 的实验环境][2]：在CentOS7-64位版本下验证非常好用，值得推广。

* [linux工具---用qemu调试linux内核 ][3]，高版本的linux，未验证，高版本现在有Yocto项目值得推广。

[1]: http://www.oldlinux.org/download/clk011c-3.0.pdf
[2]: http://www.tinylab.org/take-5-minutes-to-build-linux-0-11-experiment-envrionment/
[3]: http://blog.chinaunix.net/uid-26009923-id-3825761.html


