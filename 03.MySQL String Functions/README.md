# MySQL String Functions

This document provides an overview of various string functions available in MySQL, along with examples to demonstrate their usage.

## 1. **CHAR_LENGTH() / CHARACTER_LENGTH()**
- **Description**: Returns the number of characters in a string.
- **Syntax**: `CHAR_LENGTH(string)` or `CHARACTER_LENGTH(string)`
- **Example**:
  ```sql
  SELECT CHAR_LENGTH('Hello, World!'); -- Output: 13
  SELECT CHARACTER_LENGTH('¡Hola!');  -- Output: 6
  ```

## 2. **CONCAT()**
- **Description**: Concatenates two or more strings.
- **Syntax**: `CONCAT(string1, string2, ..., stringN)`
- **Example**:
  ```sql
  SELECT CONCAT('MySQL', ' ', 'Functions'); -- Output: MySQL Functions
  ```

## 3. **CONCAT_WS()**
- **Description**: Concatenates strings with a separator.
- **Syntax**: `CONCAT_WS(separator, string1, string2, ..., stringN)`
- **Example**:
  ```sql
  SELECT CONCAT_WS('-', '2025', '01', '17'); -- Output: 2025-01-17
  ```

## 4. **FIELD()**
- **Description**: Returns the index position of a string within a list of strings.
- **Syntax**: `FIELD(string, string1, string2, ..., stringN)`
- **Example**:
  ```sql
  SELECT FIELD('b', 'a', 'b', 'c', 'd'); -- Output: 2
  ```

## 5. **FIND_IN_SET()**
- **Description**: Returns the position of a string within a comma-separated list of strings.
- **Syntax**: `FIND_IN_SET(string, string_list)`
- **Example**:
  ```sql
  SELECT FIND_IN_SET('b', 'a,b,c,d'); -- Output: 2
  ```

## 6. **LOWER() / LCASE()**
- **Description**: Converts a string to lowercase.
- **Syntax**: `LOWER(string)` or `LCASE(string)`
- **Example**:
  ```sql
  SELECT LOWER('HELLO'); -- Output: hello
  SELECT LCASE('WORLD'); -- Output: world
  ```

## 7. **UPPER() / UCASE()**
- **Description**: Converts a string to uppercase.
- **Syntax**: `UPPER(string)` or `UCASE(string)`
- **Example**:
  ```sql
  SELECT UPPER('hello'); -- Output: HELLO
  SELECT UCASE('world'); -- Output: WORLD
  ```

## 8. **LEFT()**
- **Description**: Extracts the leftmost characters from a string.
- **Syntax**: `LEFT(string, length)`
- **Example**:
  ```sql
  SELECT LEFT('MySQL', 3); -- Output: MyS
  ```

## 9. **RIGHT()**
- **Description**: Extracts the rightmost characters from a string.
- **Syntax**: `RIGHT(string, length)`
- **Example**:
  ```sql
  SELECT RIGHT('MySQL', 3); -- Output: SQL
  ```

## 10. **LPAD()**
- **Description**: Pads the left side of a string with another string until a specified length is reached.
- **Syntax**: `LPAD(string, length, pad_string)`
- **Example**:
  ```sql
  SELECT LPAD('7', 5, '0'); -- Output: 00007
  ```

## 11. **RPAD()**
- **Description**: Pads the right side of a string with another string until a specified length is reached.
- **Syntax**: `RPAD(string, length, pad_string)`
- **Example**:
  ```sql
  SELECT RPAD('7', 5, '0'); -- Output: 70000
  ```

## 12. **TRIM()**
- **Description**: Removes leading and trailing spaces (or specified characters) from a string.
- **Syntax**: `TRIM([{BOTH | LEADING | TRAILING} [remstr] FROM] string)`
- **Example**:
  ```sql
  SELECT TRIM('  Hello  '); -- Output: Hello
  SELECT TRIM(BOTH 'x' FROM 'xxHelloxx'); -- Output: Hello
  ```

## 13. **REPLACE()**
- **Description**: Replaces all occurrences of a substring within a string with another substring.
- **Syntax**: `REPLACE(string, from_substring, to_substring)`
- **Example**:
  ```sql
  SELECT REPLACE('www.example.com', 'example', 'mysql'); -- Output: www.mysql.com
  ```

## 14. **REVERSE()**
- **Description**: Reverses the characters in a string.
- **Syntax**: `REVERSE(string)`
- **Example**:
  ```sql
  SELECT REVERSE('MySQL'); -- Output: LQSyM
  ```

## 15. **SUBSTRING() / SUBSTR()**
- **Description**: Extracts a portion of a string.
- **Syntax**: `SUBSTRING(string, start_position, length)` or `SUBSTR(string, start_position, length)`
- **Example**:
  ```sql
  SELECT SUBSTRING('Hello, World!', 8, 5); -- Output: World
  ```

## 16. **INSTR()**
- **Description**: Returns the position of the first occurrence of a substring in a string.
- **Syntax**: `INSTR(string, substring)`
- **Example**:
  ```sql
  SELECT INSTR('Hello, World!', 'World'); -- Output: 8
  ```

## 17. **LOCATE()**
- **Description**: Similar to `INSTR()`, finds the position of the first occurrence of a substring in a string.
- **Syntax**: `LOCATE(substring, string[, start_position])`
- **Example**:
  ```sql
  SELECT LOCATE('World', 'Hello, World!'); -- Output: 8
  ```

## 18. **FORMAT()**
- **Description**: Formats a number as a string with commas for thousands and a specified number of decimals.
- **Syntax**: `FORMAT(number, decimal_places)`
- **Example**:
  ```sql
  SELECT FORMAT(12345.6789, 2); -- Output: 12,345.68
  ```

## 19. **SPACE()**
- **Description**: Returns a string consisting of spaces.
- **Syntax**: `SPACE(number)`
- **Example**:
  ```sql
  SELECT CONCAT('Hello', SPACE(5), 'World'); -- Output: Hello     World
  ```

## 20. **STRCMP()**
- **Description**: Compares two strings and returns -1, 0, or 1.
- **Syntax**: `STRCMP(string1, string2)`
- **Example**:
  ```sql
  SELECT STRCMP('apple', 'banana'); -- Output: -1 (apple < banana)
  
