# 📚 Libft

[![42 School](https://img.shields.io/badge/42-School-000000?style=flat&logo=42&logoColor=white)](https://42.fr/)
[![Language](https://img.shields.io/badge/Language-C-blue.svg)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Standard](https://img.shields.io/badge/Standard-C99-orange.svg)](https://en.wikipedia.org/wiki/C99)
[![Norm](https://img.shields.io/badge/42-Norm-purple.svg)](https://github.com/42School/norminette)

## 📋 Description

**Libft** is the first project of the **42 School** curriculum, designed to create a comprehensive library of standard C functions. This project serves as the foundation for all subsequent C projects at 42, providing a solid understanding of memory management, string manipulation, and algorithmic thinking.

The library reimplements essential functions from the C standard library (`libc`) and introduces additional utility functions for enhanced functionality. All functions are coded from scratch following the strict **42 Norm** coding standards.

### Project Objectives

- **Master C fundamentals**: Pointers, memory allocation, and data structures
- **Understand standard library**: Reimplementation of `libc` functions
- **Memory management**: Safe allocation and deallocation practices
- **Code quality**: Following 42 Norm standards and best practices
- **Algorithmic thinking**: Efficient implementation of common algorithms

## 🛠️ Compilation

```bash
# Compile the library
make

# Clean object files
make clean

# Clean everything
make fclean

# Re-compile completely
make re

# Compile with bonus functions
make bonus
```

## 🚀 Usage

### Including in Your Project

```c
#include "libft.h"

// Link with: gcc -L. -lft your_file.c
```

### Basic Example

```c
#include "libft.h"

int main(void)
{
    char    *str;
    char    **split;
    int     i;

    // String duplication
    str = ft_strdup("Hello, 42!");
    ft_putstr_fd(str, 1);
    
    // String splitting
    split = ft_split("one,two,three", ',');
    i = 0;
    while (split[i])
    {
        ft_putendl_fd(split[i], 1);
        free(split[i++]);
    }
    free(split);
    free(str);
    return (0);
}
```

## 📚 Function Categories

### 🔤 Character Classification & Conversion

| Function | Description | Standard Equivalent |
|----------|-------------|-------------------|
| `ft_isalpha` | Check if alphabetic character | `isalpha` |
| `ft_isdigit` | Check if numeric character | `isdigit` |
| `ft_isalnum` | Check if alphanumeric character | `isalnum` |
| `ft_isascii` | Check if ASCII character | `isascii` |
| `ft_isprint` | Check if printable character | `isprint` |
| `ft_toupper` | Convert to uppercase | `toupper` |
| `ft_tolower` | Convert to lowercase | `tolower` |

### 🧮 String Manipulation

| Function | Description | Standard Equivalent |
|----------|-------------|-------------------|
| `ft_strlen` | Calculate string length | `strlen` |
| `ft_strchr` | Locate character in string | `strchr` |
| `ft_strrchr` | Locate character in string (reverse) | `strrchr` |
| `ft_strncmp` | Compare strings (n characters) | `strncmp` |
| `ft_strnstr` | Locate substring | `strnstr` |
| `ft_strdup` | Duplicate string | `strdup` |
| `ft_substr` | Extract substring | - |
| `ft_strjoin` | Concatenate strings | - |
| `ft_strtrim` | Trim characters from string | - |
| `ft_split` | Split string by delimiter | - |

### 🧠 Memory Management

| Function | Description | Standard Equivalent |
|----------|-------------|-------------------|
| `ft_memset` | Fill memory with byte | `memset` |
| `ft_bzero` | Zero memory | `bzero` |
| `ft_memcpy` | Copy memory | `memcpy` |
| `ft_memmove` | Move memory (overlap-safe) | `memmove` |
| `ft_memchr` | Locate byte in memory | `memchr` |
| `ft_memcmp` | Compare memory | `memcmp` |
| `ft_calloc` | Allocate zeroed memory | `calloc` |

### 🔄 String/Number Conversion

| Function | Description | Standard Equivalent |
|----------|-------------|-------------------|
| `ft_atoi` | ASCII to integer | `atoi` |
| `ft_itoa` | Integer to ASCII | - |
| `ft_strmapi` | Apply function to string | - |
| `ft_striteri` | Apply function to string (indexed) | - |

### 📤 Output Functions

| Function | Description | Standard Equivalent |
|----------|-------------|-------------------|
| `ft_putchar_fd` | Output character to fd | - |
| `ft_putstr_fd` | Output string to fd | - |
| `ft_putendl_fd` | Output string + newline to fd | - |
| `ft_putnbr_fd` | Output number to fd | - |

### 🔗 Bonus: Linked Lists

| Function | Description |
|----------|-------------|
| `ft_lstnew` | Create new list element |
| `ft_lstadd_front` | Add element to list front |
| `ft_lstsize` | Count list elements |
| `ft_lstlast` | Get last element |
| `ft_lstadd_back` | Add element to list back |
| `ft_lstdelone` | Delete one element |
| `ft_lstclear` | Delete entire list |
| `ft_lstiter` | Iterate through list |
| `ft_lstmap` | Apply function to list |

## 🏗️ Data Structures

### Linked List Structure

```c
typedef struct s_list
{
    void            *content;
    struct s_list   *next;
}                   t_list;
```

### Memory Allocation Functions

```c
// Safe allocation with automatic zero initialization
void    *ft_calloc(size_t count, size_t size);

// String duplication with memory allocation
char    *ft_strdup(const char *s1);

// Extract substring with memory allocation
char    *ft_substr(char const *s, unsigned int start, size_t len);

// Join strings with memory allocation
char    *ft_strjoin(char const *s1, char const *s2);

// Split string into array
char    **ft_split(char const *s, char c);
```

## 📁 Project Structure

```
libft/
├── Makefile                    # Compilation rules
├── libft.h                     # Header file with prototypes
├── ft_isalpha.c               # Character classification
├── ft_isdigit.c
├── ft_isalnum.c
├── ft_isascii.c
├── ft_isprint.c
├── ft_strlen.c                # String functions
├── ft_memset.c                # Memory functions
├── ft_bzero.c
├── ft_memcpy.c
├── ft_memmove.c
├── ft_strlcpy.c
├── ft_strlcat.c
├── ft_toupper.c
├── ft_tolower.c
├── ft_strchr.c
├── ft_strrchr.c
├── ft_strncmp.c
├── ft_memchr.c
├── ft_memcmp.c
├── ft_strnstr.c
├── ft_atoi.c
├── ft_calloc.c
├── ft_strdup.c
├── ft_substr.c                # Additional functions
├── ft_strjoin.c
├── ft_strtrim.c
├── ft_split.c
├── ft_itoa.c
├── ft_strmapi.c
├── ft_striteri.c
├── ft_putchar_fd.c            # Output functions
├── ft_putstr_fd.c
├── ft_putendl_fd.c
├── ft_putnbr_fd.c
├── ft_lstnew_bonus.c          # Bonus: Linked lists
├── ft_lstadd_front_bonus.c
├── ft_lstsize_bonus.c
├── ft_lstlast_bonus.c
├── ft_lstadd_back_bonus.c
├── ft_lstdelone_bonus.c
├── ft_lstclear_bonus.c
├── ft_lstiter_bonus.c
└── ft_lstmap_bonus.c
```

## 🧪 Testing

### Manual Testing

```bash
# Compile test program
gcc -Wall -Wextra -Werror -L. -lft test.c -o test

# Test basic functions
./test
```

### Automated Testing Tools

```bash
# Libft Unit Tests (third-party)
git clone https://github.com/jtoty/Libftest.git
cd Libftest
./grademe.sh

# Libft War Machine
git clone https://github.com/ska42/libft-war-machine.git
cd libft-war-machine
bash grademe.sh

# 42FileChecker
git clone https://github.com/jgigault/42FileChecker.git
cd 42FileChecker
bash 42FileChecker.sh
```

### Memory Leak Testing

```bash
# Check for memory leaks
valgrind --leak-check=full --show-leak-kinds=all ./test

# Check for memory errors
valgrind --tool=memcheck ./test
```

## 🎯 Key Learning Outcomes

### Memory Management Mastery
- **Dynamic allocation**: Understanding `malloc()` and `free()`
- **Memory safety**: Preventing leaks and segmentation faults
- **Buffer management**: Safe copying and moving of memory blocks

### String Processing Expertise
- **String manipulation**: Efficient algorithms for common operations
- **Character encoding**: ASCII and extended character handling
- **Buffer overflow prevention**: Safe string operations

### Algorithmic Thinking
- **Time complexity**: O(n) vs O(n²) implementations
- **Space efficiency**: Minimizing memory usage
- **Edge case handling**: Null pointers, empty strings, boundary conditions

## 💡 Implementation Highlights

### Efficient `ft_split` Algorithm

```c
char **ft_split(char const *s, char c)
{
    // 1. Count words for array allocation
    // 2. Allocate array of string pointers
    // 3. Extract and allocate each word
    // 4. Handle memory allocation failures gracefully
}
```

### Robust Memory Functions

```c
void *ft_memmove(void *dst, const void *src, size_t len)
{
    // Handles overlapping memory regions correctly
    // Chooses direction based on pointer comparison
}
```

### Safe String Operations

```c
size_t ft_strlcpy(char *dst, const char *src, size_t dstsize)
{
    // Always null-terminates destination
    // Returns source length for truncation detection
}
```

## 🔍 42 Norm Compliance

All functions strictly follow the **42 Norm** standards:

- ✅ **25-line function limit**
- ✅ **80-character line limit**
- ✅ **No more than 5 variables per function**
- ✅ **Forbidden keywords**: `for`, `do-while`, `switch`, `goto`
- ✅ **Consistent coding style**
- ✅ **Proper function prototypes**
- ✅ **Header protection**

## 📊 Performance Benchmarks

| Function | Time Complexity | Space Complexity | Notes |
|----------|----------------|------------------|-------|
| `ft_strlen` | O(n) | O(1) | Linear scan |
| `ft_strchr` | O(n) | O(1) | Early termination |
| `ft_split` | O(n) | O(k) | k = number of words |
| `ft_lstmap` | O(n) | O(n) | Creates new list |

## 🚨 Common Pitfalls & Solutions

### Memory Leaks
```c
// ❌ Wrong: Memory leak
char *str = ft_strjoin("Hello", " World");
// Missing free(str);

// ✅ Correct: Proper cleanup
char *str = ft_strjoin("Hello", " World");
ft_putendl_fd(str, 1);
free(str);
```

### Null Pointer Handling
```c
// ✅ Always check for NULL
char *ft_strdup(const char *s1)
{
    if (!s1)
        return (NULL);
    // ... implementation
}
```

### Buffer Overflow Prevention
```c
// ✅ Use safe string functions
size_t ft_strlcpy(char *dst, const char *src, size_t dstsize)
{
    // Always ensures null termination
    // Never writes beyond buffer bounds
}
```

## 🏆 Advanced Usage Examples

### String Processing Pipeline

```c
#include "libft.h"

char *process_input(char *input)
{
    char *trimmed;
    char *upper;
    char *result;

    if (!input)
        return (NULL);
    
    trimmed = ft_strtrim(input, " \t\n");
    if (!trimmed)
        return (NULL);
    
    upper = ft_strmapi(trimmed, to_upper_mapper);
    free(trimmed);
    
    return (upper);
}
```

### Linked List Data Processing

```c
#include "libft.h"

void process_numbers(t_list *numbers)
{
    t_list *doubled;
    
    doubled = ft_lstmap(numbers, double_number, free);
    ft_lstiter(doubled, print_number);
    ft_lstclear(&doubled, free);
}
```

## 👨‍💻 Author

**Rubén Delicado** - [@rdelicado](https://github.com/rdelicado)
- 📧 rdelicad@student.42.com
- 🏫 42 Málaga
- 📅 July 2023

## 📜 License

This project is part of the 42 School curriculum and is intended for educational purposes only. The implementation follows the school's academic guidelines and coding standards.

## 🎓 42 School Integration

This **Libft** serves as the foundation for subsequent 42 projects:

- **get_next_line**: File reading with buffer management
- **ft_printf**: Formatted output implementation
- **so_long**: 2D game development
- **pipex**: Process communication
- **minishell**: Shell implementation
- **philosophers**: Concurrent programming

### Project Timeline
- **Week 1-2**: Basic functions implementation
- **Week 3**: Additional functions and string manipulation
- **Week 4**: Bonus linked list functions
- **Week 5**: Testing, debugging, and optimization

### Evaluation Criteria
- **Functionality**: All functions work as specified
- **Norm compliance**: Strict adherence to 42 coding standards
- **Memory management**: No leaks or invalid accesses
- **Error handling**: Robust input validation
- **Code quality**: Clean, readable, and maintainable code

## 📖 Additional Resources

- [42 Intranet - Libft Subject](https://projects.intra.42.fr/projects/libft)
- [C Standard Library Reference](https://en.cppreference.com/w/c)
- [42 Norm Documentation](https://github.com/42School/norminette)
- [Memory Management in C](https://www.gnu.org/software/libc/manual/html_node/Memory.html)
- [Linked Lists Tutorial](https://www.learn-c.org/en/Linked_lists)

---

*"The function of good software is to make the complex appear to be simple."* - Grady Booch

**Libft** is more than just a library; it's the foundation of your journey into systems programming. Master these fundamentals, and you'll be well-equipped for the challenges ahead in the 42 curriculum.
