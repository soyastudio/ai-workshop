## Python String Methods Cheat Sheet

### Check String Type (Return True/False)
- isalnum() → Only alphanumeric?
- isalpha() → Only letters?
- isascii() → Only ASCII characters?
- isdecimal() → Decimal digits only?
- isdigit() → Digits only (includes superscripts, etc.)
- isnumeric() → Numeric only (includes fractions, Roman numerals, etc.)
- isidentifier() → Valid Python identifier?
- islower() → All lowercase?
- isupper() → All uppercase?
- istitle() → Title case?
- isspace() → Whitespace only?
- isprintable() → Printable characters only?

### Case Transform
- capitalize() → First letter uppercase, rest lowercase 
- casefold() → Aggressive lowercase (for comparisons)
- lower() → All lowercase 
- upper() → All uppercase 
- title() → Each word starts with uppercase 
- swapcase() → Swap case (upper ↔ lower)


### Trim and Modify
- strip() → Remove whitespace (both sides)
- lstrip() → Remove whitespace (left side)
- rstrip() → Remove whitespace (right side)
- removeprefix(prefix) → If start with prefix, then remove it 
- removesuffix(suffix) → If end with suffix then remove it
- expandtabs(tabsize) → Replace \t with spaces 

### Find and Replace(Locate substrings)
- find(sub) → First index of substring (or -1 if not found)
- rfind(sub) → Last index of substring (or -1)
- index(sub) → Like find(), but raises error if not found 
- rindex(sub) → Like rfind(), but raises error 
- count(sub) → Count occurrences 
- startswith(prefix) → Check beginning 
- endswith(suffix) → Check ending
- replace(old, new) → Replace substring with another
- translate(map) → Character-by-character replacement (via str.maketrans)

### Text Format
- format(*args, **kwargs) → Advanced string formatting
- format_map(mapping) → Like format(), but takes dict directly

### Text Align (Make text pretty)
- center(width, fill) → Center with padding
- ljust(width, fill) → Left align with padding 
- rjust(width, fill) → Right align with padding 
- zfill(width) → Pad with zeros

### Split / Join
- split(sep) → Split into list (from left)
- rsplit(sep) → Split into list (from right)
- splitlines() → Split by line breaks
- partition(sep) → Split into 3 parts: before, sep, after
- rpartition(sep) → Like partition, but from right
- join(iterable) → Join iterable into a single string


### Encode / Convert
- encode(encoding) → Convert string → bytes (UTF-8 default)
- maketrans() → Create translation table (used with translate())



## Java StringBuilder Equivalent in Python

### 1. The Python Idiom: list.append() and "".join()
```python

parts = []

# Equivalent to sb.append("text");
parts.append("Hello")
parts.append(" ")
parts.append("World")

# Equivalent to sb.toString();
result = "".join(parts)
print(result) # Output: Hello World

```

### 2. The Stream Approach: io.StringIO
```python

import io

# Create the builder
builder = io.StringIO()

# Append text
builder.write("Data Line 1\n")
builder.write("Data Line 2")

# Get the final string
result = builder.getvalue()
builder.close()

```

## String/Text Tokenization
### 1. Using the Split Method
```python

text = "Geek and Knowledge are best friends"
tokens = text.split()
print(tokens)

```

### 2. Using NLTK's word_tokenize()
```python

import nltk
from nltk.tokenize import word_tokenize

nltk.download('punkt')

text = "Geek and Knowledge are best friends"
tokens = word_tokenize(text)
print(tokens)

```

### 3. Using Regex with re.findall()
```python
import re

text = "Geek and Knowledge are best friends"
tokens = re.findall(r'\w+', text)
print(tokens)

```

### 4. Using str.split() in Pandas
```python
import pandas as pd

df = pd.DataFrame({"text": ["Geek and Knowledge are best friends"]})
df['tokens'] = df['text'].str.split()
print(df['tokens'][0])

```

### 5. Using Gensim’s tokenize()
```python
from gensim.utils import tokenize

text = "Geek and Knowledge are best friends"
tokens = list(tokenize(text))
print(tokens)
```

