# php_filter
###php参数过滤类

##Use
$filter = Filter::instance();
$data = $_GET['a'];
var_dump($filter->filter(NULL,'d'));

##Laravel/Lumen Use
move filter.php to app/Libs

add
"autoload": {
	"files": [
		"app/Helpers/functions.php"
	]
},
in composer.json

add
<?php
if (!function_exists('filter')) {
	function filter($value, $type) {
		$filter = \Libs\Filter::instance();
		return $filter->filter($value, $type);
	}
}
in app/Helpers/functions.php

#use
$a = $request->get('a');
filter($a,'d');
