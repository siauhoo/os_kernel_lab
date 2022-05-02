# 编程题
实现的比较简单，修改console.rs文件中println方法

    macro_rules! println {
    ($fmt: literal $(, $($arg: tt)+)?) => {
        $crate::console::print(format_args!("\x1b[31m"));
        $crate::console::print(format_args!(concat!($fmt, "\n") $(, $($arg)+)?));
        $crate::console::print(format_args!("\x1b[0m"));
        }
    }
就可以实现彩色打印
结果如图所示：

！[实验截图](./ch1_report.png)

