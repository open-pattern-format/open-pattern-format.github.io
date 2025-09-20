# Functions

Open Pattern Format supports a set of basic functions which can be used throughout a pattern for things like conditions and values. The functions are designed to align with those found in many spreadsheet packages to make it easy to translate formulas direct from grading sheets.


## ABS

`ABS` returns the absolute value of a number. The absolute value of a number is the number without its sign.

**Syntax**

`ABS(val)`

 * **val:** The value to process *(required)*

| Example | Result |
|---|---|
| `ABS(-1)` | `1` |
| `ABS(1)` | `1` |

## AND

`AND` returns `true` if all test conditions are `true`.

**Syntax**

`AND(cond1, cond2)`

 * **cond1:** The first condition to test *(required)*
 * **cond2:** The second condition to test *(required)*

| Example | Result |
|---|---|
| `AND('true', 'true')` | `true` |
| `AND('true', 'false')` | `false` |
| `AND(EQ(1, 1), GT(10, 1))` | `true` |
| `AND(EQ(1, 2), GT(10, 1))` | `false` |

## BOOL

`BOOL` converts values of different types to a boolean value. 

This function is useful for converting strings such as `yes` and `no` to a boolean value for a condition.

Strings `"true"`, `"yes"` and `"1"` will return `true`. Strings are converted to lower case before evaluation.

Values of `1` will return `true`, anything else will return `false`.

**Syntax**

`BOOL(val)`

 * **val:** The value to process *(required)*

| Example | Result |
|---|---|
| `BOOL(1)` | `true` |
| `BOOL(22)` | `false` |
| `BOOL('No')` | `false` |
| `BOOL('yes')` | `true` |
| `BOOL('true')` | `true` |
| `BOOL('true')` | `false` |

## CEIL

`CEIL` returns a number rounded up to the desired multiple.

**Syntax**

`CEIL(val, multiple)`

 * **val:** The value to round up *(required)*
 * **multiple:** The multiple to round up to *(default: 1)*

| Example | Result |
|---|---|
| `CEIL(3.7, 2)` | `4` |
| `CEIL(4.2)` | `5` |
| `CEIL(9, 4)` | `12` |
| `CEIL(1.22, 0.2)` | `1.4` |

## CHOOSE

`CHOOSE` returns a given value based on an index.

This is useful for returning a value such as stich count based on size.

Index starts at 1.

**Syntax**

`CHOOSE(index, values)`

 * **index:** The index of the desired value *(required)*
 * **values:** An array of values in the form `[0,1,2,3]` *(required)*

| Example | Result |
|---|---|
| `CHOOSE(2, [5, 6, 7, 8])` | `6` |
| `CHOOSE(4, ['true', 'true', 'false', 'true'])` | `true` |

## EQ

`EQ` tests whether one value is equal to another.

A single value or an array of values in the form `[0,1,2,3]` can be provided to test against.

All strings will be converted to lower case before comparison so doing case sensitive comparisons is not possible.

**Syntax**

`EQ(val, test)`

 * **val:** The value to test *(required)*
 * **test:** The value or values to test against *(required)*

| Example | Result |
|---|---|
| `EQ(1, 24)` | `false` |
| `EQ(-1, -1)` | `true` |
| `EQ(23, [21,22,23,24])` | `true` |
| `EQ(1, [0,2,4,5])` | `false` |
| `EQ('Test', 'test')` | `true` |

## FLOOR

`FLOOR` returns a number rounded down to the desired multiple.

**Syntax**

`FLOOR(val, multiple)`

 * **val:** The value to round down *(required)*
 * **multiple:** The multiple to round down to *(default: 1)*

| Example | Result |
|---|---|
| `FLOOR(3.7, 2)` | `2` |
| `FLOOR(4.8)` | `4` |
| `FLOOR(9, 2)` | `8` |

## GT

`GT` returns whether one number is greater than another.

**Syntax**

`GT(val, test)`

 * **val:** The value to test *(required)*
 * **test:** The value to test against *(required)*

| Example | Result |
|---|---|
| `GT(3.7, 5)` | `false` |
| `GT(5, 2)` | `true` |

## IF

`IF` returns the specified value based on a given condition.

**Syntax**

`IF(condition, valueT, valueF)`

 * **condition:** The test condition *(required)*
 * **valueT:** Value to return if condition is true *(required)*
 * **valueF:** Value to return if condition is false *(required)*

| Example | Result |
|---|---|
| `IF(true, 1, 2)` | `1` |
| `IF(false, 1, 2)` | `2` |
| `IF(EQ(1, 2), 1.3, 2.5)` | `2.5` |

## ISEMPTY

`ISEMPTY` returns whether a variable exists or contains no value.

This function is useful for testing non-mandatory configuration values such as custom lengths so you know whether a custom value has been provided or a default value should be used.

**Syntax**

`ISEMPTY(val)`

 * **val:** The value to test *(required)*

| Example | Result |
|---|---|
| `ISEMPTY('')` | `true` |
| `ISEMPTY('stuff')` | `false` |

## LT

`LT` returns whether one number is less than another.

**Syntax**

`LT(val, test)`

 * **val:** The value to test *(required)*
 * **test:** The value to test against *(required)*

| Example | Result |
|---|---|
| `LT(3.7, 5)` | `true` |
| `LT(5, 2)` | `false` |

## MAX

`MAX` returns the largest value from those provided.

**Syntax**

`MAX(val1, val2)`

 * **val1:** The first value to compare *(required)*
 * **val2:** The second value to compare *(required)*

| Example | Result |
|---|---|
| `MAX(3, 5)` | `5` |
| `MAX(5.4, 5.6)` | `5.6` |
| `MAX(-2, 3)` | `3` |

## MIN

`MIN` returns the smallest value from those provided.

**Syntax**

`MIN(val1, val2)`

 * **val1:** The first value to compare *(required)*
 * **val2:** The second value to compare *(required)*

| Example | Result |
|---|---|
| `MIN(3, 5)` | `3` |
| `MIN(5.4, 5.6)` | `5.4` |
| `MIN(-2, 3)` | `-2` |

## MOD

`MOD` returns the remainder after a value is divided by a divisor.

**Syntax**

`MOD(val, div)`

 * **val:** The value for which you want to determine the remainder *(required)*
 * **div:** The number to divide the value by to find the remainder *(required)*

| Example | Result |
|---|---|
| `MOD(3, 2)` | `1` |
| `MOD(3, -2)` | `-1` |
| `MOD(20, 5)` | `0` |

## MROUND

`MROUND` returns a number rounded to the desired multiple.

**Syntax**

`MROUND(val, multiple)`

 * **val:** The value to round *(required)*
 * **multiple:** The multiple to round to *(default: 1)*

| Example | Result |
|---|---|
| `MROUND(1.456)` | `1` |
| `MROUND(62, 8)` | `64` |
| `MROUND(1.3, 0.2)` | `1.4` |
| `MROUND(10, 3)` | `9` |

## MULTIPLE

`MULTIPLE` returns whether a value is a multiple of a given number.

0 is a multiple of all numbers.

**Syntax**

`MULTIPLE(val, multiple)`

 * **val:** The value to test *(required)*
 * **multiple:** The multiple to test against *(default: 1)*

| Example | Result |
|---|---|
| `MULTIPLE(10, 0)` | `true` |
| `MULTIPLE(30, 10)` | `true` |
| `MULTIPLE(30, 4)` | `false` |

## NEQ

`NEQ` tests whether one value is not equal to another.

A single value or an array of values in the form `[0,1,2,3]` can be provided to test against.

All strings will be converted to lower case before comparison so doing case sensitive comparisons is not possible.

**Syntax**

`NEQ(val, test)`

 * **val:** The value to test *(required)*
 * **test:** The value or values to test against *(required)*

| Example | Result |
|---|---|
| `NEQ(1, 24)` | `true` |
| `NEQ(-1, -1)` | `false` |
| `NEQ(23, [21,22,23,24])` | `false` |
| `NEQ(1, [0,2,4,5])` | `true` |
| `NEQ('Test', 'test')` | `false` |

## NOT

`NOT` returns the opposite of a given value so `true` becomes `false`.

**Syntax**

`NOT(val)`

 * **val:** The value to process *(required)*

| Example | Result |
|---|---|
| `NOT('true')` | `false` |
| `NOT('false')` | `true` |
| `NOT(EQ(1, 1))` | `false` |
| `NOT(LT(10, 1))` | `true` |

## OR

`OR` returns `true` if any test conditions are `true`.

**Syntax**

`OR(cond1, cond2)`

 * **cond1:** The first condition to test *(required)*
 * **cond2:** The second condition to test *(required)*

| Example | Result |
|---|---|
| `OR('true', 'false')` | `true` |
| `OR('false', 'false')` | `false` |
| `OR(EQ(1, 3), GT(10, 1))` | `true` |

## ROUND

The `ROUND` function rounds a decimal value to the nearest whole number. It is useful for converting floating point values to integer after operations such as division.

**Syntax**

`ROUND(val)`

 * **val:** The value to round *(required)*

| Example | Result |
|---|---|
| `ROUND(1.456)` | `1` |
| `ROUND(1.5)` | `2` |
| `ROUND(2.7)` | `3` |