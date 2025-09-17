---
theme: default
#background: '#ffffff' Using Default Colors
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Data Structures in R
  Essential building blocks for data analysis
drawings:
  persist: false
transition: slide-left
title: Data Structures in R
mdc: true
---

# Data Structures in R

Essential building blocks for data analysis

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: default
---

# Overview

<div class="grid grid-cols-3 gap-8 pt-30">

<div class="text-center">
  <div class="text-4xl mb-4">📊</div>
  <h3>Vectors</h3>
  <p class="text-sm opacity-75">One-dimensional arrays</p>
</div>

<div class="text-center">
  <div class="text-4xl mb-4">📋</div>
  <h3>Lists</h3>
  <p class="text-sm opacity-75">Flexible containers</p>
</div>

<div class="text-center">
  <div class="text-4xl mb-4">🔢</div>
  <h3>Data Frames</h3>
  <p class="text-sm opacity-75">Tabular data</p>
</div>

</div>

---
layout: default
---

# Vectors
*One-dimensional arrays of the same data type*

<div class="grid grid-cols-2 gap-8">

<div>

### Creating Vectors

````md magic-move
```r
# Create numeric vector
numbers <- c(1, 2, 3, 4, 5)
numbers
```

```r
# Create numeric vector
numbers <- c(1, 2, 3, 4, 5)
numbers
# [1] 1 2 3 4 5
```

```r
# Character vector
names <- c("Alice", "Bob", "Carol")
names
```

```r
# Character vector
names <- c("Alice", "Bob", "Carol")
names
# [1] "Alice" "Bob"   "Carol"
```

```r
# Sequences
seq_nums <- 1:5
seq_nums
```

```r
# Sequences
seq_nums <- 1:5
seq_nums
# [1] 1 2 3 4 5
```
````

</div>

<div>

### Vector Operations

````md magic-move
```r
# Indexing first element
numbers <- c(10, 20, 30, 40, 50)
numbers[1]
```

```r
# Indexing first element
numbers <- c(10, 20, 30, 40, 50)
numbers[1]
# [1] 10
```

```r
# Vectorized operations
numbers * 2
```

```r
# Vectorized operations
numbers * 2
# [1]  20  40  60  80 100
```

```r
# Vector arithmetic
c(1, 2, 3) + c(4, 5, 6)
```

```r
# Vector arithmetic
c(1, 2, 3) + c(4, 5, 6)
# [1] 5 7 9
```
````

</div>

</div>

<div class="mt-6 p-3 bg-blue rounded">
<strong>Key Point:</strong> All elements must be the same type
</div>

---
layout: default
---

# Lists
*Flexible containers that can hold different data types*

<div class="grid grid-cols-2 gap-8">

<div>

### Creating Lists

````md magic-move
```r
# Create a simple list
my_list <- list(
  numbers = c(1, 2, 3),
  text = "Hello"
)
my_list
```

```r
# Create a simple list
my_list <- list(
  numbers = c(1, 2, 3),
  text = "Hello"
)
my_list
# $numbers
# [1] 1 2 3
# 
# $text
# [1] "Hello"
```

```r
# Named list with mixed types
student <- list(
  name = "John",
  age = 20,
  grades = c(85, 90, 78)
)
str(student)
```

```r
# Named list with mixed types
student <- list(
  name = "John",
  age = 20,
  grades = c(85, 90, 78)
)
str(student)
# List of 3:
#  $ name  : chr "John"
#  $ age   : num 20
#  $ grades: num [1:3] 85 90 78
```
````

</div>

<div>

### Accessing Elements

````md magic-move
```r
# Using $ operator
student <- list(name = "John", age = 20)
student$name
```

```r
# Using $ operator
student <- list(name = "John", age = 20)
student$name
# [1] "John"
```

```r
# Using [[]] for single elements
student[["age"]]
```

```r
# Using [[]] for single elements
student[["age"]]
# [1] 20
```

```r
# Using [] returns a list
student["name"]
```

```r
# Using [] returns a list
student["name"]
# $name
# [1] "John"
```
````

</div>

</div>

<div class="mt-6 p-3 bg-green rounded">
<strong>Key Point:</strong> Can contain any data type, including other lists
</div>

---
layout: default
---

# Data Frames
*Two-dimensional table structure with rows and columns*

<div class="grid grid-cols-2 gap-8">

<div>

### Creating Data Frames

````md magic-move
```r
# Create from vectors
df <- data.frame(
  name = c("Alice", "Bob"),
  age = c(25, 30),
  score = c(85, 92)
)
df
```

```r
# Create from vectors
df <- data.frame(
  name = c("Alice", "Bob"),
  age = c(25, 30),
  score = c(85, 92)
)
df
#    name age score
# 1 Alice  25    85
# 2   Bob  30    92
```

```r
# Check structure
str(df)
```

```r
# Check structure
str(df)
# 'data.frame': 2 obs. of 3 variables:
#  $ name : chr [1:2] "Alice" "Bob"
#  $ age  : num [1:2] 25 30
#  $ score: num [1:2] 85 92
```
````

</div>

<div>

### Accessing Data

````md magic-move
```r
# Access columns
df <- data.frame(
  name = c("Alice", "Bob"),
  age = c(25, 30)
)
df$name
```

```r
# Access columns
df <- data.frame(
  name = c("Alice", "Bob"),
  age = c(25, 30)
)
df$name
# [1] "Alice" "Bob"
```

```r
# Row and column indexing
df[1, ]  # First row
```

```r
# Row and column indexing
df[1, ]  # First row
#    name age
# 1 Alice  25
```

```r
# Subset by condition
df[df$age > 25, ]
```

```r
# Subset by condition
df[df$age > 25, ]
#  name age
# 2  Bob  30
```
````

</div>

</div>

---
layout: default
---

# Data Frame Operations

<div class="grid grid-cols-2 gap-8">

<div>

### Basic Operations

````md magic-move
```r
# Create sample data frame
df <- data.frame(
  name = c("Alice", "Bob", "Carol"),
  age = c(25, 30, 35)
)
nrow(df)
```

```r
# Create sample data frame
df <- data.frame(
  name = c("Alice", "Bob", "Carol"),
  age = c(25, 30, 35)
)
nrow(df)
# [1] 3
```

```r
# Get column names
names(df)
```

```r
# Get column names
names(df)
# [1] "name" "age"
```

```r
# Summary statistics
summary(df$age)
```

```r
# Summary statistics
summary(df$age)
#    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
#      25      27      30      30      32      35
```
````

</div>

<div>

### Modification

````md magic-move
```r
# Add new column
df$new_col <- df$age * 2
df
```

```r
# Add new column
df$new_col <- df$age * 2
df
#    name age new_col
# 1 Alice  25      50
# 2   Bob  30      60
# 3 Carol  35      70
```

```r
# Add new row
new_row <- data.frame(
  name = "David", 
  age = 28,
  new_col = 56
)
df <- rbind(df, new_row)
tail(df, 2)
```

```r
# Add new row
new_row <- data.frame(
  name = "David", 
  age = 28,
  new_col = 56
)
df <- rbind(df, new_row)
tail(df, 2)
#    name age new_col
# 3 Carol  35      70
# 4 David  28      56
```
````

</div>

</div>

---
layout: center
---

# Comparison Summary

| Feature | Vector | List | Data Frame |
|---------|--------|------|------------|
| **Dimensions** | 1D | 1D | 2D |
| **Data Types** | Homogeneous | Heterogeneous | Mixed by column |
| **Access** | `[i]` | `$`, `[[]]`, `[]` | `$`, `[i,j]` |
| **Use Case** | Simple arrays | Complex structures | Tabular data |

---
layout: center
class: text-center
---

# Best Practices

<div class="grid grid-cols-1 gap-6 pt-8 max-w-4xl mx-auto">

<div class="p-6 bg-blue rounded-lg">
<h3 class="text-lg font-semibold mb-2">Choose the Right Structure</h3>
<p class="text-sm">Vectors for simple arrays, Lists for complex nested data, Data Frames for datasets</p>
</div>

<div class="p-6 bg-green rounded-lg">
<h3 class="text-lg font-semibold mb-2">Consistent Naming</h3>
<p class="text-sm">Use clear, descriptive names for columns and list elements</p>
</div>

<div class="p-6 bg-purple rounded-lg">
<h3 class="text-lg font-semibold mb-2">Type Awareness</h3>
<p class="text-sm">Understand data types to avoid unexpected coercion</p>
</div>

</div>

---
layout: center
class: text-center
---

# Thank You

<div class="pt-12">
  <div class="text-6xl mb-8">✈️🏢🏢</div>
  <h2 class="text-2xl mb-4">Ciao Niggggas</h2>
  <p class="opacity-75">Master these data structures for effective data analysis</p>
</div>

<div class="pt-8">
  <span class="text-sm opacity-50">
    Press ESC to exit presentation mode
  </span>
</div>