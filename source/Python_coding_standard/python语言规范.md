# python语言规范

20220512

https://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_language_rules/

模块名写法: module_name ;  
包名写法: package_name ;  
类名: ClassName ;  
方法名: method_name ;  
异常名: ExceptionName ;  
函数名: function_name ;  
全局常量名: GLOBAL_CONSTANT_NAME ;  
全局变量名: global_var_name ;  
实例名: instance_var_name ;  
函数参数名: function_parameter_name ;  
局部变量名: local_var_name .   

函数名,变量名和文件名应该是描述性的,尽量避免缩写,特别要避免使用非项目人员不清楚难以理解的缩写,不要通过删除单词中的字母来进行缩写. 始终使用 .py 作为文件后缀名,不要用破折号.

即使是一个打算被用作脚本的文件, 也应该是可导入的. 并且简单的导入不应该导致这个脚本的主功能(main functionality)被执行, 这是一种副作用. 主功能应该放在一个main()函数中.

如果你正在编辑代码, 花几分钟看一下周边代码, 然后决定风格. 如果它们在所有的算术操作符两边都使用空格, 那么你也应该这样做. 如果它们的注释都用标记包围起来, 那么你的注释也要这样.

制定风格指南的目的在于让代码有规可循, 这样人们就可以专注于”你在说什么”, 而不是”你在怎么说”. 我们在这里给出的是全局的规范, 但是本地的规范同样重要. 如果你加到一个文件里的代码和原有代码大相径庭, 它会让读者不知所措. 避免这种情况.

https://www.jianshu.com/p/8b6c425b65a6  
函数的参数列表中，默认值等号两边不要添加空格
