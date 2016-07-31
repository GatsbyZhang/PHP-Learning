# PHP-Learning
PHP的学习笔记
chapter 1
	利用纯HTML web页面，服务器只能提供静态HTML，而静态HTML只能显示内容。要把网站变成交互式web应用，
web服务器必须扮演一个更具动态性的角色，而PHP将这个角色变成可能。通过引入PHP，web服务器可以动态地生成HTML web页面。
  		
	PHP代码在服务器上运行，它们存储在PHP脚本中，扩展名是 .php。PHP脚本包含HTML代码和CSS代码，服务器运行PHP脚本的结果就是返回纯HTML和CSS。

	表单使用HTML的<form>标记创建，其action属性中设置的文件使服务器按照该文件处理表单，
所以可以将PHP脚本文件作为form的action属性值，与表单相连处理表单数据：
<form action= “report.php”  method= “post”> </from>

	多数PHP脚本包含PHP代码和HTML代码，HTML代码不作处理，PHP代码在服务器运行后产生HTML代码。

		<?php 和 ?>包围PHP代码。
		每个PHP语句以；结束；
		如果页面中有PHP代码，文件扩展名最好为.php而不是.html。
		变量命名规则：PHP变量名以$开头，长度至少一个字符，$后第一个字符可以是字母或下划线_，
此后的字符可以是字母。下划线和数字。空格和其他除下划线和$的特殊字符不允许出现在变量名中。
		变量命名习惯：变量名区分大小写，一般使用小写字母；用下划线分隔多个单词。
		未赋值的变量是null，在JS中是undefined.

		$_POST是一个特殊的变量，成为超级全局变量，这是PHP内置的，在整个脚本中都可以使用，不必显式创建。
$_POST是一种特殊的PHP存储容器，称为数组，提交表单时，表单域中的数据就存储到$_POST数组中，每个元素对
应一个表单域。访问表单域的数据就是通过表单域的域名，这就实现了表单数据到PHP的传递。

	echo命令用于将信息作为HTML输出， 点号‘.’用于将字符串和变量连接，变量包含数字时会先转化为字符串。
	PHP中的转义字符：单引号（\’）双引号（\”）换行（\n）。换行符必须用在单引号中，关于引号还有一个特点：
单引号包围的字符串被认为是原始文本，而PHP处理双引号包围的字符串时会寻找变量，并直接插入变量值，省去了
点号连接。单引号串只支持\’和\\转义字符，所有其他转义字符只能出现在双引号串中。

	mail($to, $subject, $msg): $to email address;  $subject消息主题；$msg消息体。
要调用mail()函数时指定发送者，还需要一个额外的函数参数，并用串连接：
mail($to, $subject, $msg, ‘From:’ . $email);
