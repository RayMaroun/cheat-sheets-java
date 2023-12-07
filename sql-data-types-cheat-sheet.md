## SQL Data Types Cheat Sheet

1. **Numeric Types:**

   - **INT**: A standard integer, typically supporting a range of -2147483648 to 2147483647.
   - **TINYINT**: A very small integer, with a range of -128 to 127.
   - **SMALLINT**: A small integer, with a range of -32768 to 32767.
   - **MEDIUMINT**: A medium-sized integer, with a range of -8388608 to 8388607.
   - **BIGINT**: A large integer, with a range of -9223372036854775808 to 9223372036854775807.
   - **DECIMAL(M,D)**: A fixed-point number. M is the maximum number of digits (the precision) and D is the number of digits to the right of the decimal point (the scale).
   - **FLOAT(M,D)**: A single-precision floating-point number. M is the total number of digits and D is the number of digits after the decimal.
   - **DOUBLE(M,D)**: A double-precision floating-point number.

2. **Date and Time Types:**

   - **DATE**: A date in the format YYYY-MM-DD.
   - **TIME**: A time in the format HH:MM:SS.
   - **DATETIME**: A combination of date and time in the format YYYY-MM-DD HH:MM:SS.
   - **TIMESTAMP**: Similar to DATETIME, but used for values that contain both date and time. Automatically updates to the current date and time when the row is modified.
   - **YEAR**: A year in two-digit or four-digit format.

3. **String Types:**

   - **CHAR(M)**: A fixed-length string with a maximum length of 255 characters. M specifies the column length in characters.
   - **VARCHAR(M)**: A variable-length string with a maximum length of 65535 characters.
   - **TEXT**: A text column with a maximum length of 65535 characters.
   - **BLOB**: A binary large object that can hold a variable amount of data.

4. **Binary Types:**

   - **BINARY(M)**: Similar to CHAR(M) but stores binary byte strings.
   - **VARBINARY(M)**: Similar to VARCHAR(M) but stores binary byte strings.

5. **Enumerated Types:**

   - **ENUM('value1', 'value2', ...)**: A string object that can only have one value, chosen from a list of possible values.

6. **Set Types:**
   - **SET('value1', 'value2', ...)**: Similar to ENUM but can store zero or more values from a specified list.
