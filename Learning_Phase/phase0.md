# Phase 0 — AI Engineering Foundations

## Overview

Phase 0 builds the practical foundations needed before moving into Math for AI → Machine Learning → Deep Learning → NLP → GenAI → AI Engineering → Agentic AI Engineering.

The goal was to close foundation gaps efficiently without re-learning tools already used hands-on.

---

# 1. Python for AI — DONE

## Core Python

- Variables and data types: `int`, `float`, `str`, `bool`, `None`
- Variables are names/references to objects
- `type()` and `id()`
- Functions: parameters vs arguments, `return` vs `print`, defaults, keyword arguments, `*args`, `**kwargs`
- Local vs global scope

## Core Data Structures

- Lists, tuples, sets, dictionaries
- Nested lists/dictionaries
- List and dictionary comprehensions
- `enumerate()`
- `split()` / `join()`
- Slicing

## Python Object Model

- Everything is an object
- References/names
- `==` vs `is`
- Mutable vs immutable objects
- Aliasing
- Shallow vs deep copy
- `copy.deepcopy()`

## OOP and Recursion

- Classes, objects, attributes, methods, constructors
- Base case and recursive case
- Recursion vs iteration

## Hashing

- Hash tables
- Dictionary lookup: O(1) average
- Set membership: O(1) average
- Hash collisions
- Hashable vs unhashable objects
- Frequency maps

## Iterators and Generators

An iterable can produce an iterator:

```python
iterator = iter(data)
value = next(iterator)
```

Generators use `yield` and produce values lazily:

```python
def numbers():
    yield 1
    yield 2
    yield 3
```

Useful for memory efficiency, streaming, and large data pipelines.

## Decorators

Decorators add behavior without changing a function's core implementation:

```python
from functools import wraps

def logger(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        print("Function started")
        result = func(*args, **kwargs)
        print("Function finished")
        return result
    return wrapper
```

`@logger` is equivalent to:

```python
add = logger(add)
```

Relevant to logging, caching, retries, FastAPI, and middleware-style behavior.

## Context Managers

Main pattern:

```python
with open("file.txt") as f:
    data = f.read()
```

Mental model:

- `__enter__()` → setup
- body executes
- `__exit__()` → cleanup

## Type Hints

Covered:

```python
name: str
age: int
scores: list[float]
data: dict[str, float]
value: str | None
```

Also introduced `Callable` and typed function signatures.

## Async Python

Foundation only:

```python
async def fetch_data():
    result = await some_operation()
    return result
```

Deeper async concepts are deferred to backend/AI engineering.

---

# 2. NumPy — DONE

NumPy is the numerical-computing foundation for Python-based ML.

## Creating Arrays

```python
import numpy as np

np.array([1, 2, 3])
np.zeros((2, 3))
np.ones((2, 3))
np.arange(1, 10)
np.linspace(0, 1, 5)
```

## Array Properties

```python
x.shape
x.ndim
x.size
x.dtype
```

Mental model:

- `shape` → dimensions
- `ndim` → number of dimensions
- `size` → total elements
- `dtype` → element type

## Indexing and Slicing

```python
x[row, column]
x[:, 0]
x[0, :]
```

## Reshape

```python
x.reshape(3, 2)
x.reshape(2, -1)
```

## Vectorization

NumPy performs element-wise operations directly:

```python
result = values * 2
```

Vectorization is important because ML works with large numerical arrays.

## Aggregation

```python
x.sum()
x.mean()
x.min()
x.max()
x.std()
```

## Axis

```python
x.sum(axis=0)  # per column
x.sum(axis=1)  # per row
```

Mental model:

- `axis=0` → down rows → result per column
- `axis=1` → across columns → result per row

## Broadcasting

Dimensions are compared from the right. Dimensions are compatible when they are equal, one is `1`, or the dimension is absent.

Example:

```python
x + np.array([10, 20, 30])
```

## Boolean Masking

```python
x[x > 25]
x[(x > 10) & (x < 30)]
```

Use `&`, `|`, `~` for NumPy array conditions.

## Matrix Multiplication

```python
A @ B
```

Shape rule:

```text
(m, n) @ (n, p) → (m, p)
```

Inner dimensions must match.

## Transpose

```python
A.T
```

## ML Connection

A common ML operation is:

```text
X @ W + b
```

This foundation leads directly into linear algebra, neural networks, embeddings, attention, and transformers.

---

# 3. Pandas — DONE

Pandas is used for data manipulation, cleaning, analysis, and preprocessing.

## Series and DataFrame

```python
import pandas as pd

s = pd.Series([10, 20, 30])

df = pd.DataFrame({
    "name": ["Alice", "Bob"],
    "age": [25, 30]
})
```

## Inspecting Data

```python
df.head()
df.tail()
df.shape
df.columns
df.dtypes
df.info()
df.describe()
```

## Selecting Data

```python
df["age"]
df[["name", "age"]]
```

`iloc` is position-based:

```python
df.iloc[0, 1]
```

`loc` is label-based:

```python
df.loc[0, "age"]
```

## Filtering

```python
df[df["age"] > 30]

df[(df["age"] > 30) & (df["salary"] > 60000)]
```

## Creating Columns

```python
df["salary_lakhs"] = df["salary"] / 100000
```

## Missing Values

```python
df.isna()
df.isna().sum()
df.dropna()
df["age"] = df["age"].fillna(df["age"].median())
```

## Sorting

```python
df.sort_values(by="salary", ascending=False)
```

## GroupBy

```python
df.groupby("department")["salary"].mean()

df.groupby("department")["salary"].agg(["min", "max", "mean"])
```

## Apply

```python
df["category"] = df["salary"].apply(
    lambda x: "High" if x >= 80000
    else "Medium" if x >= 60000
    else "Low"
)
```

## Merge

```python
employees.merge(details, on="employee_id", how="left")
```

Covered inner, left, right, and outer joins.

## Duplicates

```python
df.duplicated()
df.drop_duplicates()
```

## Rename and Types

```python
df.rename(columns={"old": "new"})
df["age"].astype(int)
```

## String Operations

```python
df["name"].str.upper()
df["name"].str.lower()
df["name"].str.strip()
df["name"].str.contains("a")
df["name"].str.len()
```

## Datetime

```python
df["joining_date"] = pd.to_datetime(df["joining_date"])
df["year"] = df["joining_date"].dt.year
df["month"] = df["joining_date"].dt.month
df["day"] = df["joining_date"].dt.day
```

## Pandas ↔ NumPy

```python
X = df[["age", "salary"]].to_numpy()
```

## Feature / Target Split

```python
X = df[["age", "salary"]]
y = df["target"]
```

`X` → features  
`y` → target

## One-Hot Encoding

```python
pd.get_dummies(
    df["department"],
    prefix="dept",
    drop_first=True
)
```

---

# 4. Matplotlib — DONE

Matplotlib is the visualization layer for EDA and ML.

```python
import matplotlib.pyplot as plt
```

## Line Plot

```python
plt.plot(x, y)
plt.title("Growth")
plt.xlabel("Days")
plt.ylabel("Value")
plt.show()
```

Use for trends and continuous progression.

## Scatter Plot

```python
plt.scatter(age, salary)
plt.title("Age vs Salary")
plt.xlabel("Age")
plt.ylabel("Salary")
plt.show()
```

Use for relationships and feature-vs-target visualization.

## Histogram

```python
plt.hist(salary, bins=5)
plt.title("Salary Distribution")
plt.xlabel("Salary")
plt.ylabel("Frequency")
plt.show()
```

Use for distributions, spread, and outlier inspection.

## Bar Chart

```python
plt.bar(departments, employees)
plt.title("Employees by Department")
plt.xlabel("Department")
plt.ylabel("Employees")
plt.show()
```

Use for categorical comparisons.

### Four plots to remember

| Plot        | Main use                |
| ----------- | ----------------------- |
| `plot()`    | Trends                  |
| `scatter()` | Relationships           |
| `hist()`    | Distributions           |
| `bar()`     | Categorical comparisons |

Typical ML flow:

```text
Data → EDA → Visualization → Patterns/Outliers → Feature Engineering → ML Model
```

---

# 5. Probability Fundamentals — DONE

Probability gives ML a language for uncertainty.

## Probability

Probability ranges from `0` to `1`:

```text
0   → impossible
0.5 → 50% chance
1   → certain
```

## Experiment, Outcome, Event

- **Experiment** → process we perform/observe
- **Outcome** → one possible result
- **Event** → collection of outcomes of interest

Example:

```text
Die outcomes = {1,2,3,4,5,6}
Even event = {2,4,6}
P(even) = 3/6 = 0.5
```

## Conditional Probability

```text
P(A | B)
```

means probability of A given B.

Formula:
\[
P(A|B)=rac{P(A∩B)}{P(B)}
\]

Core intuition:

> What is the probability of A after I already know B?

## Independence

Events are independent when knowing one does not change the probability of the other.

For independent events:
\[
P(A∩B)=P(A)P(B)
\]

## Bayes' Theorem

\[
P(A|B)=rac{P(B|A)P(A)}{P(B)}
\]

Mental model:

```text
Prior belief
    ↓
New evidence
    ↓
Updated belief
    ↓
Posterior belief
```

## Random Variable

A variable whose value depends on a random process.

Example:

```text
X = result of rolling a die
X ∈ {1,2,3,4,5,6}
```

## Expected Value

Expected value is essentially the long-run average.

For a fair die:
\[
E[X] = 1(1/6)+2(1/6)+...+6(1/6)=3.5
\]

## Variance

Variance measures how spread out values are around the mean.

Example:

```text
A = [49, 50, 51]
B = [10, 50, 90]
```

Both have mean 50, but B has much greater variance.

## Standard Deviation

\[
Std=\sqrt{Variance}
\]

## Normal Distribution

A common bell-shaped distribution characterized by:

- Mean `μ` → center
- Standard deviation `σ` → spread

Not every ML dataset is normally distributed.

## Probability → ML / GenAI

Examples:

```text
P(spam | email)
P(disease | patient data)
P(next_token | previous_tokens)
```

Generative AI uses probability distributions over possible tokens:

```text
Prompt
 ↓
Probability distribution
 ↓
Token selection
 ↓
Next token
 ↓
Probability distribution
 ↓
...
```

Important distinction:

> A model's predicted probability is not automatically a guarantee about real-world certainty. Calibration and related concepts come later.

---

# 6. Already Hands-On — Kept for Revision

These were intentionally not re-taught:

- Jupyter 🟢
- Git/GitHub 🟢
- Linux 🟢
- SQL 🟢
- APIs / JSON 🟢

They can be reviewed briefly at the end of Phase 0 when useful.

---

# 7. Phase 0 Final Checklist

```text
Python                 ✅ DONE
NumPy                  ✅ DONE
Pandas                 ✅ DONE
Matplotlib             ✅ DONE
Probability intuition  ✅ DONE

Jupyter                🟢 Already hands-on
Git/GitHub              🟢 Already hands-on
Linux                  🟢 Already hands-on
SQL                    🟢 Already hands-on
APIs / JSON            🟢 Already hands-on
```

# 8. Phase 0 Mental Models

- **Python:** Variables are references to objects.
- **NumPy:** Numerical data is represented as arrays and processed efficiently with vectorized operations.
- **Pandas:** DataFrames are structured datasets that we clean, transform, analyze, and prepare for ML.
- **Matplotlib:** Visualization helps us understand data before modeling.
- **Probability:** Probability gives ML a language for uncertainty.

---

# 9. Next Phase — Math for AI

The next phase goes deeper than the probability intuition covered here.

```text
Math for AI
    │
    ├── 1. Statistics & Probability
    ├── 2. Linear Algebra
    ├── 3. Calculus
    └── 4. Optimization
             ↓
       Machine Learning
             ↓
       Deep Learning
             ↓
            NLP
             ↓
           GenAI
             ↓
      AI Engineering
             ↓
   Agentic AI Engineering
```

Learning style:

```text
Intuition
   ↓
Why it matters
   ↓
Math / Formula
   ↓
Python implementation
   ↓
ML connection
   ↓
Exercises
   ↓
Interview perspective
```

# Phase 0 Status: ✅ COMPLETE
