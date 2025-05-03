# PPCalendar Code Style Guide

## Table of Contents
1. [Philosophy](##philosophy)
1. [General Principles](#general-principles)
1. [Python Specifics](#python-specifics)
1. [Type Annotations](#type-annotations)
1. [Documentation](#documentation)
1. [Testing](#testing)
1. [Commit Messages](##commit-messages)

## Philosophy

```python
# Values:
- Clarity over cleverness
- Consistency over personal preference
- Maintainability over brevity
- Explicit over implicit
```

## General Principles

### 1. Structure
- Keep functions under 25 lines
- Limit modules to ~300 lines
- Use vertical whitespace liberally
- One clear purpose per function/class

### 2. Naming
```python
# Good
def render_month_header(month: int) -> str:

# Bad
def hdr(m: int) -> str:
```

- **Variables**: `lower_snake_case`
- **Functions**: `lower_snake_case()`
- **Constants**: `UPPER_SNAKE_CASE`
- **Classes**: `UpperCamelCase`

## Python Specifics

### 1. Formatting
```python
# Yes
def calculate_size(
    width: int,
    height: int,
    margin: int = 10
) -> tuple[int, int]:

# No
def calculate_size(width: int, height: int, margin: int = 10) -> tuple[int, int]:
```

- Line length: 88 chars (Black-compatible)
- Use f-strings over `.format()`
- Avoid backslash line continuation

### 2. Imports
```python
# Stdlib first
import calendar

from datetime import date
from typing import Optional

# Then third-party
import numpy as np

# Then local
from .utils import seasonal_color
```

## Type Annotations

### 1. Basics
```python
def greet(name: str, times: int = 1) -> None:
```

### 2. Advanced
```python
from typing import Union, Optional

def process(
    data: Union[str, bytes],
    modifier: Optional[callable] = None
) -> list[str]:
```

## Documentation

### 1. Docstrings (Google Style)
```python
def calculate_area(width: float, height: float) -> float:
    """Calculate rectangular area.
    
    Args:
        width: The horizontal dimension
        height: The vertical dimension
        
    Returns:
        The computed area in square units
        
    Raises:
        ValueError: If either dimension is negative
    """
```

### 2. Inline Comments
```python
# Only use when business logic isn't obvious
result = x * 1.2  # Apply 20% premium
```

---

*"Code is read much more often than it is written."*  

— Guido van Rossum

