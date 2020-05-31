# PHP Throwable Tree

PHP 7.x introduces new Throwable interface together Error and Exception.

```bash
Throwable
+-- Error
|   +-- ArithmeticError
|   |   +-- DivisionByZeroError
|   +-- AssertionError
|   +-- ParseError
|   +-- TypeError
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

## Example code

| Name           | Example                                                                                     |
| :------------- | :------------------------------------------------------------------------------------------ |
| LogicException | [LogicException.php](../src/ThrowableTree/LogicException.php "View LogicException Example") |
