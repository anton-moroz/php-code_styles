# PHP code style rules

## Comments
PHP doc comments should be written before each method, property or constant in a next way:
```php
/**
 * @param string $testParam
 * @param int    $testParam2
 *
 * @return bool
 * @throws Exception
 */
 ```
 
 When adding comments to code, there must be empty line before first line and they must start with `// `, FE:
 ```php
 $uri = urldecode(parse_url($_SERVER['REQUEST_URI'], PHP_URL_PATH));

// This file allows us to emulate Apache's "mod_rewrite" functionality from the
// built-in PHP web server. This provides a convenient way to test a Laravel
// application without having installed a "real" web server software here.
if ($uri !== '/' && file_exists(__DIR__.'/public'.$uri)) {
    return false;
}
```

## Code blocks
Code blocks like `if`, `for`, `foreach`, `while`, `try`, `catch` etc should be separated with other code with empty lines.
No empty line is needed between parent and nested code blocks. FE:
```php
$ships = Ship::all();

foreach ($ships as $ship) {
    if ($ship->isCargo()) {
        continue;        
    }
  
    if ($ship->isLiner()) {
        echo $ship->name();
    }
}

return true;
```

## Class uses
All classes should be used, no cases when /ClassName is used.

```php
use Exception;

...

/**
 * @throws Exception
 */
```
is preferred over
```php
...

/**
 * @throws /Exception
 */
```

## Reused Values
Values that are used in several places should be saved to constants, configs/env variables, translations.

## Naming Conventions
Variables, class properties and methods should use camelCase.
- Classes and namespaces - PascalCase.
- Database table fields - snake_case.
- Constants - SNAKE_CASE_CAPS.

## Arrays
All the arrays should be declared using `[]` instead of `array()`
```php
$list = ['item1', 'item2'];
```
