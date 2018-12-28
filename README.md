# php_filter
## This is a php parameter filter class

## Use
```
$filter = Filter::instance();
$a = $_GET['a'];
var_dump($filter->filter($a,'d'));
```
**the second parameter supports the following parameters：**
+ 'd' => int
+ 's' => string
+ 'a' => array
+ 'f' => float
+ 'b' => bool

## Use in Laravel/Lumen

### move filter.php to app/Libs

### Copy the following code to composer.json
```
"autoload": {
	"files": [
		"app/Helpers/functions.php"
	]
},
```


### Copy the following code to app/Helpers/functions.php, if file non-existent, you can create it.
```
<?php
if (!function_exists('filter')) {
	function filter($value, $type) {
		$filter = \Libs\Filter::instance();
		return $filter->filter($value, $type);
	}
}
```

### Use in code
```
$a = $request->get('a');
filter($a,'d');
```


Modification based on thinkPHP 5
