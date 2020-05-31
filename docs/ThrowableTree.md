# PHP Throwable Tree

PHP 7.x introduces new Throwable interface together Error and Exception.

PHP 7.3 over:

```bash
Throwable (Interface)
+-- Error
|   +-- ArithmeticError
|   |   +-- DivisionByZeroError
|   +-- AssertionError
|   +-- CompileError
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

// AssertionError

ini_set('assert.exception', 1);
assert(2 < 1);

// output
// PHP Fatal error:  Uncaught AssertionError: assert(2 < 1) in...

```

## Runtime Exceptions

| Name           | Example                                                                                     |
| :------------- | :------------------------------------------------------------------------------------------ |
| LogicException | [LogicException.php](../src/ThrowableTree/LogicException.php "View LogicException Example") |
