In shell scripting, the `if` statement supports various conditional checks using test operators. Below are some common options that can be used in an `if` statement:

### 1. **File Tests**
These are used to check for file attributes:

| Option  | Description                                               |
|---------|-----------------------------------------------------------|
| `-f`    | True if the file exists and is a regular file.             |
| `-d`    | True if the path exists and is a directory.                |
| `-e`    | True if the file or directory exists.                      |
| `-L`    | True if the file exists and is a symbolic link.            |
| `-r`    | True if the file exists and is readable.                   |
| `-w`    | True if the file exists and is writable.                   |
| `-x`    | True if the file exists and is executable.                 |
| `-s`    | True if the file exists and its size is greater than zero. |

### 2. **String Tests**
These are used to compare strings:

| Option             | Description                                  |
|--------------------|----------------------------------------------|
| `-z "$var"`        | True if the string is empty.                 |
| `-n "$var"`        | True if the string is not empty.             |
| `"$str1" = "$str2"`| True if strings are equal.                   |
| `"$str1" != "$str2"`| True if strings are not equal.               |

### 3. **Numeric Comparisons**
Used for integer comparisons:

| Option        | Description                                   |
|---------------|-----------------------------------------------|
| `n1 -eq n2`   | True if integers `n1` and `n2` are equal.     |
| `n1 -ne n2`   | True if integers `n1` and `n2` are not equal. |
| `n1 -gt n2`   | True if `n1` is greater than `n2`.            |
| `n1 -lt n2`   | True if `n1` is less than `n2`.               |
| `n1 -ge n2`   | True if `n1` is greater than or equal to `n2`.|
| `n1 -le n2`   | True if `n1` is less than or equal to `n2`.   |

### 4. **Logical Operators**
You can combine multiple conditions using logical operators:

| Option  | Description                                 |
|---------|---------------------------------------------|
| `-a`    | Logical AND. True if both conditions are true.|
| `-o`    | Logical OR. True if at least one condition is true.|
| `!`     | Logical NOT. Negates the condition.          |

### Example

```bash
if [ -f "$file" ] && [ -r "$file" ]; then
    echo "File exists and is readable"
elif [ -d "$dir" ]; then
    echo "$dir is a directory"
else
    echo "File does not exist or is not readable"
fi
```

In this example:
- `-f` checks if it's a regular file.
- `-r` checks if the file is readable.
- `-d` checks if the path is a directory.
