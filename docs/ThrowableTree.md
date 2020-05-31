# PHP Throwable Tree

PHP 7.x introduces new Throwable interface together Error and Exception.

```bash
Interface Throwable
+-- Error
|   +-- ArithmeticError
|   |   +-- DivisionByZeroError
|   +-- AssertionError
|   +-- CompileError (PHP 7.3 over)
|       +-- ParseError
|   +-- TypeError
|       +-- ArgumentCountError
+-- Exception
    +-- ClosedGeneratorException
    +-- DOMException
    +-- ErrorException
    +-- IntlException
    +-- LogicException
    |   +-- BadFunctionCallException
    |   |   +-- BadMethodCallException
    |   +-- DomainException
    |   +-- InvalidArgumentException
    |   +-- LengthException
    |   +-- OutOfRangeException
    +-- PharException
    +-- ReflectionException
    +-- RuntimeException
        +-- mysqli_sql_exception
        +-- OutOfBoundsException
        +-- OverflowException
        +-- PDOException
        +-- RangeException
        +-- UnderflowException
        +-- UnexpectedValueException
```

## ArithmeticError

```php
<?php

intdiv(PHP_INT_MIN, -1);

// output
// Fatal error: Uncaught ArithmeticError: Division of PHP_INT_MIN by -1 is not an integer
```

## DivisionByZeroError

```php
<?php

var_dump(0%0);

// output
// PHP Fatal error:  Uncaught DivisionByZeroError: Modulo by zero in %s line %d

```

## AssertionError

```php
<?php

ini_set('assert.exception', 1);
assert(2 < 1);

// output
// PHP Fatal error:  Uncaught AssertionError: assert(2 < 1) in...

```

## ArgumentCountError

```php
<?php

declare(strict_types=1); //if without this, not exception but error

$a = [1,2=>[3,4]];

count($a, COUNT_RECURSIVE, 'throw error');

// output
// PHP Fatal error:  Uncaught ArgumentCountError: count() expects at most 2 parameters, 3 given
```

## TypeError

```php
<?php

a('throw error');

function a(int $b) {}

// output
// PHP Fatal error:  Uncaught TypeError: Argument 1 passed to a() must be of the type int, string given
```

## Runtime Exceptions

| Name           | Example                                                                                     |
| :------------- | :------------------------------------------------------------------------------------------ |
| LogicException | [LogicException.php](../src/ThrowableTree/LogicException.php "View LogicException Example") |
