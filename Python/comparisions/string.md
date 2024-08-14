Here's a comparison of string operations across Java, Swift, and Python:

### 1. **Basic String Operations**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Create String**                   | `String str = "Hello";`                   | `let str = "Hello"`                         | `str = "Hello"`                  |
| **Get String Length**               | `int length = str.length();`              | `let length = str.count`                    | `length = len(str)`              |
| **Concatenate Strings**             | `String result = str1 + str2;`            | `let result = str1 + str2`                  | `result = str1 + str2`           |
| **Append String**                   | `str = str.concat("World");`              | `str.append("World")`                       | `str += "World"`                 |
| **Access Character by Index**       | `char ch = str.charAt(0);`                | `let ch = str[str.index(str.startIndex, offsetBy: 0)]` | `ch = str[0]`             |
| **Check if String is Empty**        | `boolean empty = str.isEmpty();`          | `let empty = str.isEmpty`                   | `empty = not str`                |
| **Convert to Uppercase**            | `String upper = str.toUpperCase();`       | `let upper = str.uppercased()`              | `upper = str.upper()`            |
| **Convert to Lowercase**            | `String lower = str.toLowerCase();`       | `let lower = str.lowercased()`              | `lower = str.lower()`            |
| **Trim Whitespace**                 | `String trimmed = str.trim();`            | `let trimmed = str.trimmingCharacters(in: .whitespaces)` | `trimmed = str.strip()` |

### 2. **Substring Operations**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Get Substring by Indexes**        | `String sub = str.substring(1, 4);`       | `let start = str.index(str.startIndex, offsetBy: 1); let end = str.index(str.startIndex, offsetBy: 4); let sub = String(str[start..<end])` | `sub = str[1:4]` |
| **Get Substring from Index**        | `String sub = str.substring(2);`          | `let start = str.index(str.startIndex, offsetBy: 2); let sub = String(str[start...])` | `sub = str[2:]`   |

### 3. **Searching and Matching**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Find Character/Substring Index**  | `int index = str.indexOf("e");`           | `if let index = str.firstIndex(of: "e") { ... }` | `index = str.find("e")`    |
| **Check if String Contains Substring** | `boolean contains = str.contains("He");` | `let contains = str.contains("He")`        | `contains = "He" in str`         |
| **Check if String Starts with Substring** | `boolean starts = str.startsWith("He");`| `let starts = str.hasPrefix("He")`         | `starts = str.startswith("He")`  |
| **Check if String Ends with Substring** | `boolean ends = str.endsWith("lo");`    | `let ends = str.hasSuffix("lo")`           | `ends = str.endswith("lo")`      |
| **Count Occurrences of Substring**  | `int count = str.split("e", -1).length - 1;` | `let count = str.filter { $0 == "e" }.count` | `count = str.count("e")`     |

### 4. **String Replacement**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Replace Substring**               | `String replaced = str.replace("e", "a");` | `let replaced = str.replacingOccurrences(of: "e", with: "a")` | `replaced = str.replace("e", "a")` |
| **Replace First Occurrence**        | *No direct equivalent*                    | `let replaced = str.replacingOccurrences(of: "e", with: "a", options: [], range: str.range(of: "e"))` | `replaced = str.replace("e", "a", 1)` |

### 5. **Splitting and Joining Strings**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Split String**                    | `String[] parts = str.split(" ");`        | `let parts = str.split(separator: " ")`     | `parts = str.split(" ")`         |
| **Join Strings**                    | `String joined = String.join(" ", list);` | `let joined = parts.joined(separator: " ")` | `joined = " ".join(parts)`       |

### 6. **String Formatting**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Format String**                   | `String formatted = String.format("Hello, %s!", name);` | `let formatted = "Hello, \(name)!"` | `formatted = f"Hello, {name}!"`  |
| **Format Number as String**         | `String formatted = String.format("%.2f", number);` | `let formatted = String(format: "%.2f", number)` | `formatted = f"{number:.2f}"` |

### 7. **String Conversion**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Convert Number to String**        | `String str = Integer.toString(123);`     | `let str = String(123)`                     | `str = str(123)`                 |
| **Convert Boolean to String**       | `String str = Boolean.toString(true);`    | `let str = String(true)`                    | `str = str(True)`                |
| **Convert String to Integer**       | `int num = Integer.parseInt(str);`        | `let num = Int(str)`                        | `num = int(str)`                 |
| **Convert String to Float**         | `float num = Float.parseFloat(str);`      | `let num = Float(str)`                      | `num = float(str)`               |

### 8. **Character Operations**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Convert Char to String**          | `String str = Character.toString(ch);`    | `let str = String(ch)`                      | `str = str(ch)`                  |
| **Check if Char is Digit**          | `boolean isDigit = Character.isDigit(ch);` | `let isDigit = ch.isNumber`                | `isDigit = ch.isdigit()`         |
| **Check if Char is Letter**         | `boolean isLetter = Character.isLetter(ch);` | `let isLetter = ch.isLetter`              | `isLetter = ch.isalpha()`        |

### 9. **String Encoding and Decoding**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Encode String to Bytes**          | `byte[] bytes = str.getBytes("UTF-8");`   | `let bytes = Array(str.utf8)`               | `bytes = str.encode("utf-8")`    |
| **Decode Bytes to String**          | `String str = new String(bytes, "UTF-8");` | `let str = String(decoding: bytes, as: UTF8.self)` | `str = bytes.decode("utf-8")` |

### 10. **Miscellaneous**

| **Functionality**                   | **Java (`String`)**                       | **Swift (`String`)**                        | **Python (`str`)**               |
|-------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **String Hash Code**                | `int hash = str.hashCode();`              | `let hash = str.hashValue`                  | `hash = hash(str)`               |

This table provides a quick comparison of string operations in Java, Swift, and Python, showcasing the similarities and differences across these languages.